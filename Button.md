### The button click show the random number 1 to 6

````
Button(onClick = { result = (1..6).random() })

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
### Click

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
            
### Click button Preview and Next show image
````
fun ShowImage(modifier: Modifier = Modifier) {

    val images = listOf(
        R.drawable.image1,
        R.drawable.img_20240117_082842,
        R.drawable.image3,
        R.drawable.image2,
        R.drawable.ic_launcher_background
        // Add more image resource IDs as needed
    )

    var currentIndex by remember { mutableStateOf(0) }

    Column(

    ) {
        Image(
            painter = painterResource(id = images[currentIndex]),
            contentDescription = null,
        )
        // Buttons Row
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp),
            horizontalArrangement = Arrangement.SpaceBetween
        ) {
            // Preview Button
            Button(
                onClick = {
                    // Handle Preview button click
                    currentIndex = (currentIndex - 1).coerceIn(0, images.size - 1)

                }
            ) {
                Text(text = stringResource(R.string.preview))
            }

            // Next Button
            Button(
                onClick = {
                    // Handle Next button click

                    currentIndex = (currentIndex + 1).coerceIn(0, images.size - 1)
                }
            ) {
                Text(text = stringResource(R.string.next))
            }
        }

    }
}
````
### Button Click to go Next Activity 
````
     Button(
            onClick = {
                mContext.startActivity(Intent(mContext,MainActivity::class.java))
             }
        ) {
            Text(text = stringResource(R.string.go_to_main_activity))
        }
````
