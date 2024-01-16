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
      Text(
        text = stringResource(R.string.calculate_tip),
           modifier = Modifier
               .padding(bottom = 16.dp, top = 40.dp)
               .align(alignment = Alignment.Start)
       )
      EditNumberField(
         value = amountInput, // get the value
           onValueChange = {amountInput = it}, // show the value in textBox
           modifier = Modifier
           .padding(bottom = 32.dp)
     )
   }
}
