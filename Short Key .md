### Creates a MutableState object, which holds a value that can be changed.
 ### Its initial value is set to 1.


````
 var result by remember { mutableStateOf(1) }

````
### The button has moved down in the center of the image

````
 Column(
            modifier = modifier,
            horizontalAlignment = Alignment.CenterHorizontally
        ) {

for example


         Image(
                painter = painterResource(id = imageResources),
                contentDescription = result.toString()
            )
            Button(onClick = { result = (1..6).random() }) {
                Text(stringResource(R.string.roll))

            }
        }
    }
````
### Center

````

 Column(
        horizontalAlignment = Alignment.CenterHorizontally,
        modifier = Modifier
            .fillMaxSize()
            .wrapContentSize(Alignment.Center)
    ){

    write the code here

}
````
### click Image

````
 var result by remember { mutableStateOf(1) }


 when (imageShow) {

            1 -> {
                Image(
                    painter = painterResource(R.drawable.lemon_tree),
                    contentDescription = null,
                    modifier = Modifier
                        .clickable {
                            imageShow = 2
                        }
                )
                Text(text = stringResource(R.string.Lemon_tree))
            }

            2 -> {
                Image(painter = painterResource(id = R.drawable.lemon_squeeze),
                    contentDescription = null,
                    modifier = Modifier
                        .clickable {
                            imageShow = 1
                        }
                )
                Text(text = stringResource(id = R.string.lemon_squeeze))
            }
````
###  Conversion to decimal number

````
 val amount = amountInput.toDoubleOrNull()?:0.0
````
val amount =: This declares a new variable named amount and assigns it a value.
amountInput.toDoubleOrNull(): This part attempts to convert the value of the variable amountInput to a Double (a decimal number type). If the conversion is successful, it returns a Double value. If the conversion fails (e.g., because amountInput isn't a valid number), it returns null.

