### Add TextField
````
@Composable
fun EditNumberField(
    value : String,
    onValueChange:(String) -> Unit,
    modifier: Modifier = Modifier
) {
    TextField(
        value = value,
        onValueChange =  onValueChange,
        singleLine = true,
        label = { Text(stringResource(R.string.bill_amount)) },
        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Number),
        modifier = modifier
    )
}

````
````
@Composable
fun TipTime(){
   Column(
      modifier = Modifier
          .statusBarsPadding()
          .padding(horizontal = 40.dp)
          .safeDrawingPadding(),
       horizontalAlignment = Alignment.CenterHorizontally,
       verticalArrangement = Arrangement.Center
   ) {
      EditNumberField(
         value = amountInput,
           onValueChange = {amountInput = it},
           modifier = Modifier
           .padding(bottom = 32.dp)
     )
   }
}
