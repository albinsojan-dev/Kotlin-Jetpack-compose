### Add leading icon to text fields (optional)

````
@Composable
fun EditNumberField(

    @DrawableRes leadingIcon: Int,
   
)
````

````
TextField(
    value = value,
    leadingIcon = { Icon(painter = painterResource(id = leadingIcon), null) },
    //...
)
````
````
EditNumberField(
    label = R.string.bill_amount,
    leadingIcon = R.drawable.money,
    // Other arguments
)
````
