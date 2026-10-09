# Especificación de Componentes

## Introducción
Este documento detalla los componentes clave de la interfaz de usuario de "FinanApp", incluyendo sus estados, comportamientos y requisitos de accesibilidad. La especificación está diseñada para garantizar consistencia en la experiencia del usuario y para facilitar la implementación por parte del equipo de desarrollo.

## Componentes

### 1. Botón Primario

**Descripción**: Botón utilizado para acciones principales en la interfaz, como "Guardar", "Aceptar" o "Continuar".

**Estados**:

| Estado       | Descripción                                                                 | Visualización                                                                                     |
|--------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Default**  | Estado inicial del botón.                                                  | ![#4CAF50](https://via.placeholder.com/15/4CAF50/000000?text=+) Fondo: `#4CAF50`
Texto: `#FFFFFF`
Borde: `1px solid #4CAF50`
Radio: `4px`
Padding: `12px 24px` |
| **Hover**    | Estado cuando el usuario pasa el cursor sobre el botón.                    | ![#45a049](https://via.placeholder.com/15/45a049/000000?text=+) Fondo: `#45a049`
Texto: `#FFFFFF`
Borde: `1px solid #45a049`
Radio: `4px`
Padding: `12px 24px` |
| **Focus**    | Estado cuando el botón está enfocado (para navegación con teclado).        | ![#4CAF50](https://via.placeholder.com/15/4CAF50/000000?text=+) Fondo: `#4CAF50`
Texto: `#FFFFFF`
Borde: `2px solid #2E7D32`
Radio: `4px`
Padding: `12px 24px` |
| **Disabled** | Estado cuando el botón está deshabilitado y no puede interactuarse.        | ![#CCCCCC](https://via.placeholder.com/15/CCCCCC/000000?text=+) Fondo: `#CCCCCC`
Texto: `#666666`
Borde: `1px solid #CCCCCC`
Radio: `4px`
Padding: `12px 24px` |
| **Loading**  | Estado cuando el botón está procesando una acción.                        | ![#4CAF50](https://via.placeholder.com/15/4CAF50/000000?text=+) Fondo: `#4CAF50`
Texto: `#FFFFFF`
Borde: `1px solid #4CAF50`
Radio: `4px`
Padding: `12px 24px`
Spinner: `2px #FFFFFF` |
| **Error**    | Estado cuando la acción asociada al botón falla.                           | ![#F44336](https://via.placeholder.com/15/F44336/000000?text=+) Fondo: `#F44336`
Texto: `#FFFFFF`
Borde: `1px solid #F44336`
Radio: `4px`
Padding: `12px 24px` |

**Comportamiento**:
- El botón debe ser **clickeable** en los estados `Default`, `Hover` y `Focus`.
- En el estado `Loading`, el botón debe mostrar un spinner y deshabilitar la interacción.
- En el estado `Error`, el botón debe mostrar un mensaje de error breve (ej. "Error al guardar") y permitir reintentar la acción.

**Accesibilidad**:
- El botón debe tener un `aria-label` descriptivo si el texto no es suficiente.
- El estado `Focus` debe ser claramente visible para usuarios que navegan con teclado.
- El contraste entre el texto y el fondo debe cumplir con WCAG 2.2 (mínimo 4.5:1).

---

### 2. Campo de Texto

**Descripción**: Campo utilizado para ingresar información textual, como nombres, descripciones o montos.

**Estados**:

| Estado       | Descripción                                                                 | Visualización                                                                                     |
|--------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Default**  | Estado inicial del campo.                                                  | Fondo: `#FFFFFF`
Texto: `#333333`
Borde: `1px solid #CCCCCC`
Radio: `4px`
Padding: `12px`
Placeholder: `#999999` |
| **Focus**    | Estado cuando el campo está enfocado.                                      | Fondo: `#FFFFFF`
Texto: `#333333`
Borde: `2px solid #2196F3`
Radio: `4px`
Padding: `12px` |
| **Error**    | Estado cuando el campo contiene un error de validación.                   | Fondo: `#FFFFFF`
Texto: `#333333`
Borde: `2px solid #F44336`
Radio: `4px`
Padding: `12px`
Mensaje de error: `#F44336` |
| **Disabled** | Estado cuando el campo está deshabilitado.                                 | Fondo: `#F5F5F5`
Texto: `#999999`
Borde: `1px solid #E0E0E0`
Radio: `4px`
Padding: `12px` |

**Comportamiento**:
- El campo debe permitir la entrada de texto en el estado `Default`.
- En el estado `Focus`, el campo debe mostrar un borde destacado para indicar que está activo.
- En el estado `Error`, el campo debe mostrar un mensaje de error debajo del campo (ej. "Este campo es obligatorio").
- El campo debe soportar validaciones en tiempo real (ej. formato de correo electrónico, longitud mínima).

**Accesibilidad**:
- El campo debe tener una etiqueta (`label`) asociada con `for` y `id`.
- El mensaje de error debe estar asociado al campo con `aria-describedby`.
- El contraste entre el texto y el fondo debe cumplir con WCAG 2.2.

---

### 3. Tarjeta de Resumen

**Descripción**: Componente utilizado para mostrar información resumida, como el saldo actual, gastos mensuales o ingresos.

**Estados**:

| Estado       | Descripción                                                                 | Visualización                                                                                     |
|--------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Default**  | Estado inicial de la tarjeta.                                               | Fondo: `#FFFFFF`
Texto: `#333333`
Borde: `1px solid #E0E0E0`
Radio: `8px`
Padding: `16px`
Sombra: `0 2px 4px rgba(0,0,0,0.1)` |
| **Hover**    | Estado cuando el usuario pasa el cursor sobre la tarjeta.                  | Fondo: `#FFFFFF`
Texto: `#333333`
Borde: `1px solid #B0BEC5`
Radio: `8px`
Padding: `16px`
Sombra: `0 4px 8px rgba(0,0,0,0.15)` |
| **Selected** | Estado cuando la tarjeta está seleccionada.                                | Fondo: `#E3F2FD`
Texto: `#333333`
Borde: `2px solid #2196F3`
Radio: `8px`
Padding: `16px`
Sombra: `0 2px 4px rgba(0,0,0,0.1)` |

**Comportamiento**:
- La tarjeta debe ser **clickeable** en el estado `Default` y `Hover`.
- En el estado `Selected`, la tarjeta debe mostrar un borde destacado para indicar selección.
- La tarjeta puede contener botones secundarios para acciones adicionales (ej. "Ver detalles").

**Accesibilidad**:
- La tarjeta debe tener un `role="button"` si es clickeable.
- El contraste entre el texto y el fondo debe cumplir con WCAG 2.2.
- Si la tarjeta contiene acciones, estas deben ser accesibles vía teclado.

---

### 4. Barra de Navegación

**Descripción**: Componente utilizado para navegar entre las diferentes secciones de la aplicación.

**Estados**:

| Estado       | Descripción                                                                 | Visualización                                                                                     |
|--------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Default**  | Estado inicial de la barra.                                                | Fondo: `#FFFFFF`
Texto: `#757575`
Borde inferior: `1px solid #E0E0E0`
Padding: `12px 0` |
| **Active**   | Estado cuando el usuario está en la sección asociada al ítem.             | Fondo: `#FFFFFF`
Texto: `#2196F3`
Borde inferior: `2px solid #2196F3`
Padding: `12px 0` |
| **Hover**    | Estado cuando el usuario pasa el cursor sobre un ítem.                    | Fondo: `#FFFFFF`
Texto: `#2196F3`
Borde inferior: `1px solid #E0E0E0`
Padding: `12px 0` |
| **Focus**    | Estado cuando el ítem está enfocado (para navegación con teclado).         | Fondo: `#FFFFFF`
Texto: `#2196F3`
Borde inferior: `2px solid #2196F3`
Padding: `12px 0`
Outline: `2px solid #2196F3` |

**Comportamiento**:
- La barra debe mostrar el ítem activo resaltado.
- Los ítems deben ser **clickeables** para navegar a las secciones correspondientes.
- La barra debe ser responsive y adaptarse a diferentes tamaños de pantalla.

**Accesibilidad**:
- Cada ítem debe tener un `aria-label` descriptivo.
- Los ítems deben ser navegables con teclado.
- El contraste entre el texto y el fondo debe cumplir con WCAG 2.2.

---

### 5. Modal de Confirmación

**Descripción**: Componente utilizado para solicitar confirmación al usuario antes de realizar una acción crítica, como eliminar un registro.

**Estados**:

| Estado       | Descripción                                                                 | Visualización                                                                                     |
|--------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Default**  | Estado inicial del modal.                                                  | Fondo del overlay: `rgba(0,0,0,0.5)`
Fondo del modal: `#FFFFFF`
Texto: `#333333`
Borde: `1px solid #E0E0E0`
Radio: `8px`
Padding: `24px` |
| **Loading**  | Estado cuando el modal está procesando la acción.                          | Fondo del overlay: `rgba(0,0,0,0.5)`
Fondo del modal: `#FFFFFF`
Texto: `#333333`
Borde: `1px solid #E0E0E0`
Radio: `8px`
Padding: `24px`
Spinner: `2px #2196F3` |

**Comportamiento**:
- El modal debe aparecer centrado en la pantalla.
- El modal debe bloquear la interacción con el resto de la aplicación (overlay).
- El modal debe incluir botones para confirmar o cancelar la acción.
- En el estado `Loading`, el modal debe mostrar un spinner y deshabilitar los botones.

**Accesibilidad**:
- El modal debe tener un `role="dialog"` y `aria-modal="true"`.
- El foco debe ser atrapado dentro del modal mientras está abierto.
- El modal debe ser cerrado con la tecla `Escape`.
- El contraste entre el texto y el fondo debe cumplir con WCAG 2.2.

## Requisitos Generales

1. **Consistencia**: Todos los componentes deben seguir las mismas convenciones de diseño, como colores, tipografía y espaciado.

2. **Responsividad**: Los componentes deben adaptarse a diferentes tamaños de pantalla, desde móviles hasta desktop.

3. **Accesibilidad**: Todos los componentes deben cumplir con los criterios de accesibilidad WCAG 2.2, incluyendo:
   - Contraste mínimo de 4.5:1 entre texto y fondo.
   - Navegación con teclado.
   - Etiquetas descriptivas para screen readers.

4. **Internacionalización**: Los componentes deben soportar texto en múltiples idiomas, con espacio suficiente para traducciones más largas.

5. **Rendimiento**: Los componentes deben ser ligeros y no afectar el rendimiento de la aplicación, especialmente en dispositivos móviles.