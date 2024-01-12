### Add Images

````
  painter = painterResource(R.drawable."IMAGE_NAME"),
            contentDescription = null,
````
### Add full Image
````
 contentScale = ContentScale.Crop,
modifier = Modifier
                .fillMaxSize()

````

### There have 6 photo we can view whichever you want
Declares a variable named imageResources to store a resource ID for an image. \
Employs a when expression to conditionally assign a value to imageResources based on the value of result. \
If result is 1, the value R.drawable.dice_1 is assigned to imageResources, indicating that the image resource for dice face 1 should be used. \
If result doesn't match any of the specified cases (meaning it's not 1 through 5), the value R.drawable.dice_6 is assigned, effectively using the image resource for dice face 6 as a default.

````
  val imageResources = when (result) {
            1 -> R.drawable.dice_1
            2 -> R.drawable.dice_2
            3 -> R.drawable.dice_3
            4 -> R.drawable.dice_4
            5 -> R.drawable.dice_5
            else -> R.drawable.dice_6
        }
````
