## Código HTML:
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>

<body>
    <header>
        <img src="./vegetables-resources/img/banner1.png">
    </header>
    <main>
        <section>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/potato.png">
                    <p><strong>Potato</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/garlic.png">
                    <p><strong>Garlic</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/chili-pepper.png">
                    <p><strong>Chili pepper</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/bell-pepper2.png">
                    <p><strong>Bell pepper</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/mushroom.png">
                    <p><strong>Mushroom</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/eggplant2.png">
                    <p><strong>Eggplant</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/carrot.png">
                    <p><strong>Carrot</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/tomato.png">
                    <p><strong>Tomato</strong></p>
                </figure>
            </article>
            <article>
                <figure>
                    <img src="./vegetables-resources/img/cucumber.png">
                    <p><strong>Cucumber</strong></p>
                </figure>
            </article>
        </section>
    </main>
    <footer>
        <img src="./vegetables-resources/img/banner2.png">
    </footer>
</body>

</html>

## Código CSS del mismo documento HTML:
html{
    height:100%;
}

body{
    height: 100%;
    width: 100%;
    margin:0;
    display: flex;
    flex-direction: column;
}

header, footer{
    display: flex;
    justify-content: center;
}

img{
    width: 100%;
}

main {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
    padding-top: 4vw; padding-bottom: 4vw;
}

main>section{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

main>section>article{
    display: flex;
    flex-direction: column;
    text-align: center;
}

main>section>article>figure{
    background-color: rgb(224,230,166);
    border-radius: 5%;
    padding: 1vw;
    padding-bottom: 1vw;
}

main>section>article>figure>img{
    width: 21vw;
    border-style: solid;
    border: 1;
    border-radius: 10%;
    border-color: #50821B;
}

p{
    color: #50821B;
    font-size: 3vw;
}
## Código en KOTLIN:
fun main() {
   var filasMax = readln().toInt()


   while (filasMax != 0) {
       // Creamos la lista de listas (Lista2D)
       var lista2D = mutableListOf<List<String>>()


       // Basandonos en que si o si tiene que ser cuadrada, rellenamos la lista con listas
       for (item in 0 until filasMax) {
           var listaUnidemsional = readln().split(" ").filter { it.isNotBlank() }
           lista2D.add(listaUnidemsional)
       }


       var esIdentidad = 1 // "1" = SI, "0" = NO


       // Comprobamos por linea y columna
       for (linea in 0 until filasMax) {
           for (columna in 0 until filasMax) {
               // Si columna = fila estamos en la diagonal
               if (linea == columna && lista2D[linea][columna].toInt() != 1) {
                   esIdentidad = 0
               } else if( linea != columna && lista2D[linea][columna].toInt() != 0) {
                   esIdentidad = 0
               }
           }
       }


       // Procesamos y printeamos la respuesta
       if (esIdentidad == 0) {
           println("NO")
       } else {
           println("SI")
       }


       filasMax = readln().toInt()
       }
   }
