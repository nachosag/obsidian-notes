```typescript
// ==========================================
// 1. EL MODELO (El "Proveedor" de datos y estado)
// ==========================================
class EleccionesModel {
  private votos: Record<string, number> = { "Partido A": 0, "Partido B": 0 };

  // El modelo solo se preocupa por su lógica interna
  votar(partido: string): void {
    if (this.votos[partido] !== undefined) {
      this.votos[partido]++;
    }
  }

  restarVoto(partido: string): void {
    if (this.votos[partido] !== undefined && this.votos[partido] > 0) {
      this.votos[partido]--;
    }
  }

  obtenerVotos(): Record<string, number> {
    return { ...this.votos };
  }
}

// ==========================================
// 2. EL PATRÓN COMMAND (Clases de Comando)
// ==========================================
interface Comando {
  ejecutar(): void;
  deshacer(): void;
}

// Encapsula la petición de voto. El controlador no sabrá CÓMO vota el modelo.
class ComandoVotar implements Comando {
  constructor(
    private modelo: EleccionesModel, 
    private partido: string
  ) {}

  ejecutar(): void {
    this.modelo.votar(this.partido);
  }

  deshacer(): void {
    this.modelo.restarVoto(this.partido);
  }
}

// ==========================================
// 3. EL COMMAND PROCESSOR
// ==========================================
class ProcesadorComandos {
  private historial: Comando[] = [];

  ejecutar(comando: Comando): void {
    comando.ejecutar();
    this.historial.push(comando); // Guarda el comando para poder deshacerlo
  }

  deshacerUltimo(): void {
    const ultimo = this.historial.pop();
    if (ultimo) {
      ultimo.deshacer();
    }
  }
}

// ==========================================
// 4. EL CONTROLADOR DE MVC (Cliente del Comando)
// ==========================================
class TablaController {
  constructor(
    private procesador: ProcesadorComandos,
    private modelo: EleccionesModel
  ) {}

  // El controlador solo traduce el evento físico a un comando estándar
  alHacerClickVoto(nombrePartido: string): void {
    const comando = new ComandoVotar(this.modelo, nombrePartido);
    this.procesador.ejecutar(comando);
  }
}
```

Si decidimos implementar esta arquitectura con **Command Processor** y añadimos soporte para **Undo (Deshacer)** en las acciones del usuario:

- ¿Qué componente del MVC debe suscribirse al **Command Processor** para enterarse de que un comando fue "deshecho" y así actualizar la pantalla?

Analizamos cada una de las opciones y descartamos.

- **Opción A:** La Vista se suscribe directamente al Command Processor.
- **Opción B:** El Controlador se suscribe al Command Processor y fuerza el re-dibujado de la Vista.
- **Opción C:** El Modelo se entera del cambio, y la Vista simplemente reacciona a través del mecanismo tradicional de propagación de cambios.

Si la Vista se suscribe al `Command Processor`, estaríamos obligando a la Vista a conocer a otro componente más. Si el Command Processor llegase a cambiar entonces hay que cambiar la Vista. 

Si el Controlador se suscribe `Command Processor` para forzar el re-dibujado de la Vista, romperíamos el flujo natural de MVC. Básicamente, la **condicion de carrera** juega a favor del Controlador y no del Modelo, esto hace que la Vista reciba el aviso de que debe renderizarse de forma apresurada cuando los datos aun no fueron actualizados en el Modelo. Si el Controlador le pasa los datos a la Vista entonces el Modelo deja de ser el dueño de la verdad.

La respuesta correcta es: ningún componente del MVC se debe suscribir al `Command Processor` porque no es necesario. El flujo correcto es el siguiente:

1. El usuario presiona "Undo". El Controlador le pide al `Command Processor` que deshaga la acción
2. El `Command Processor` ejecuta el método `deshacer()` del Comando, el cual modifica **directamente** el estado del Modelo
3. El modelo detecta que su estado cambió y dispara su **Change-Propagation Mechanism** tradicional (`notify()`)
4. La **Vista** (que ya está suscriba al Modelo) recibe la notificación, le pide los datos actualizados al Modelo y se re-dibuja sola

- ¿Qué pasaría si el Modelo de datos no se entera del "Undo"?

Si el Modelo no se entera del "Undo" entonces el modelo nunca cambiaría de estado, por lo tanto nunca dispararía su **Change-Propagation Mechanism** y la Vista nunca recibiría la notificación y nunca se re-renderizaría.