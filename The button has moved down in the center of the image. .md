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


