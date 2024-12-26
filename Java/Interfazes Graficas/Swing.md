***'Swing' se refiere al paquete de clases que forman parte de la biblioteca grafica (GUI) de Java, conocida como Java Swing que se utiliza para crear interfaces graficas de usuarios mas avanzadas y estilizadas que las ofrecidas por AWT (Abstract Window ToolKit)***

- ***Swing esta incluido en el paquete `javax.swing` y proporciona componentes de alto nivel como ventanas, botones, menús, tablas, listas, entre otros...***

### Características de Swing:

- ***Basado en AWT: Swing extiende las capacidades de AWT y proporciona un conjunto de mayores componentes.***
- ***Plataforma Independiente: Swing es completamente escrito en Java, lo que asegura que sea independiente del sistema operativo.***
- ***Componentes ligeros: Los componentes de Swing son ligeros (lightweight), es decir, no dependen directamente del sistema operativo para renderizarse.***
- ***Modelo de eventos mejorado: Swing utiliza un modelo de delegación de eventos, que separa la lógica de los eventos de los componentes de interfaz.***
- ***Pluggable Look and Feel (L&F): Permite cambiar el aspecto visual de los componentes para adaptarse a diferentes temas o sistemas.***

### Estructura de Swing:

- ***Componentes básicos (``JComponent`` y derivados):***

| Componente   | Descripcion                             |
| ------------ | --------------------------------------- |
| JButton      | Botones interactivos                    |
| JLabel       | Etiquetas para mostrar texto o imagenes |
| JTextField   | Campos de texto para entrada de datos   |
| JTextArea    | Área de texto para entradas multilinea  |
| JCheckBox    | Casillas de verificacion                |
| JRadioButton | Botones de opción (Radio Buttons)       |
- ***Contenedores principales:***

| Componente   | Descripcion                                           |
| ------------ | ----------------------------------------------------- |
| JFrame       | Vetana Principal                                      |
| JDialog      | Cuadro de dialogo                                     |
| JPanel       | Contenedor generico para organizar otros componentes  |
| JScrollPanel | Proporciona barras de desplazamiento para componentes |
- ***Componentes avanzados:***

| Componente   | Descripcion                                   |
| ------------ | --------------------------------------------- |
| JTable       | Tablas para mostrar datos en forma tabular    |
| JTree        | Arboles para organizar informacion jerarquica |
| JTabbedPanel | Panel con pestañas                            |
| JList        | Lista de elementos                            |
- ***Menús y barras de herramientas:***

| Componente | Descripcion              |
| ---------- | ------------------------ |
| JMenuBar   | Barra de Menu            |
| JMenu      | Menu dentro de una barra |
| JToolBar   | Barra de herramientas    |
### Ejemplo basico:

```java
import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class SwingExample {
    public static void main(String[] args) {
        // Crear la ventana
        JFrame frame = new JFrame("Ejemplo de Swing");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 200);

        // Crear un botón
        JButton button = new JButton("Haz clic");
        JLabel label = new JLabel("Etiqueta inicial");
        
        // Configurar acción para el botón
        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                label.setText("¡Botón pulsado!");
            }
        });

        // Agregar componentes a la ventana
        JPanel panel = new JPanel();
        panel.add(button);
        panel.add(label);
        frame.add(panel);

        // Hacer visible la ventana
        frame.setVisible(true);
    }
}
```