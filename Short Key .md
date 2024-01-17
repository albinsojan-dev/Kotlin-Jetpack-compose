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
Example

val amountInput = "12.34"  // This is a valid number string \
val amount = amountInput.toDoubleOrNull() ?: 0.0 \
// amount will now be 12.34 

val invalidInput = "hello"  // This is not a valid number string \
val amount2 = invalidInput.toDoubleOrNull() ?: 0.0 \
// amount2 will now be 0.0


### Numerical value to format

````
   NumberFormat.getCurrencyInstance().format("value")
````
Example

double price = 12.99;  // Numerical value to format \
String formattedPrice = NumberFormat.getCurrencyInstance().format(price); \
// This would likely output "$12.99" (in the US locale) or "£12.99" (in the UK locale)

