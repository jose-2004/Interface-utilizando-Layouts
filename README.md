## INTERFAZ

Este código es un ejemplo de una interfaz de usuario en JavaFX. La clase principal, InterfaceExample, extiende la clase Application de JavaFX, que es la base de todas las aplicaciones JavaFX. El método start es llamado por el sistema cuando la aplicación está lista para comenzar, y es aquí donde se configura la interfaz de usuario. La interfaz de usuario consta de un VBox llamado leftSide que contiene 8 HBoxes, cada uno con una imagen y un campo de texto. También hay un ListView que muestra una lista de elementos de texto. Este ListView se encuentra en otro VBox llamado rightSide. Además, hay un TextField en la parte inferior de la interfaz de usuario. Todos estos elementos se agregan a un AnchorPane llamado root, que es el contenedor principal de la interfaz de usuario. Finalmente, se crea una Scene con el AnchorPane como raíz y se establece en el Stage, que es el contenedor de nivel superior de una aplicación JavaFX. El método main es el punto de entrada de la aplicación y llama al método launch(args), que inicia la aplicación JavaFX.

Codigo:
    
    public class InterfaceExample extends Application {
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.ListView;
    import javafx.scene.control.TextField;
    import javafx.scene.image.Image;
    import javafx.scene.image.ImageView;
    import javafx.scene.layout.AnchorPane;
    import javafx.scene.layout.HBox;
    import javafx.scene.layout.VBox;
    import javafx.stage.Stage;
    @Override
    public void start(Stage stage) {
        VBox leftSide = new VBox();
        leftSide.setSpacing(10); // Ajustar el espaciado entre los elementos

        for (int i = 0; i < 8; i++) {
            HBox hbox = new HBox();
            hbox.setSpacing(5); // Espaciado entre la imagen y el TextField

            // Crear y configurar la imagen
            ImageView imageView = new ImageView(new Image("usuario.png"));
            // Cambia "file:image.png" por la ruta de tu imagen
            imageView.setFitWidth(30); // Ancho de la imagen (ajustado a 30)
            imageView.setFitHeight(30); // Altura de la imagen (ajustado a 30)

            // Crear y configurar el TextField
            TextField textField = new TextField();
            textField.setPromptText("Nombre y apellido");

            // Agregar la imagen y el TextField al HBox
            hbox.getChildren().addAll(imageView, textField);

            // Agregar el HBox al VBox
            leftSide.getChildren().add(hbox);
        }

        ListView<String> listView = new ListView<>();
        listView.setPrefHeight(300); // Establecer la altura preferida del ListView
        listView.setPrefWidth(200);
       
        VBox rightSide = new VBox(listView);

        TextField bottomTextField = new TextField();
        bottomTextField.setPrefWidth(420); // Establecer el ancho preferido del último TextField

        AnchorPane root = new AnchorPane(leftSide, rightSide, bottomTextField);

        // Establecer las restricciones de anclaje para cada nodo
        AnchorPane.setLeftAnchor(leftSide, 10.0);
        AnchorPane.setTopAnchor(leftSide, 10.0);

        AnchorPane.setRightAnchor(rightSide, 10.0);
        AnchorPane.setTopAnchor(rightSide, 10.0);

        AnchorPane.setLeftAnchor(bottomTextField, 10.0);
        AnchorPane.setBottomAnchor(bottomTextField, 10.0);

        Scene scene = new Scene(root, 450, 400); // Reducir el ancho de la escena a 400

        stage.setTitle("Interface Example");
        stage.setScene(scene);
        stage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
    }



## Ejecucion

![image](https://github.com/jose-2004/Interface-utilizando-Layouts/assets/80079088/c5687619-4a08-46ab-9cee-2370dc21ce0f)

