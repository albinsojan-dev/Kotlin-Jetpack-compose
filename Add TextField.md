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
````
### Add two TextField
````
fun EditNumberField(
   @StringRes labelType: Int,
    value: String,
    onValueChanged: (String) -> Unit,
    modifier: Modifier
) {
    TextField(
        value = value,
        singleLine = true,
        modifier = modifier,
        onValueChange = onValueChanged,
        label = { Text(text = stringResource(labelType))},
        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Number)
    )
}
````
````
EditNumberField(
            labelType = R.string.bill_amount,
            value = amountInput,
            onValueChanged = { amountInput = it },
            modifier = Modifier
                .padding(bottom = 32.dp)
                .fillMaxWidth()
        )
        EditNumberField(
            labelType = R.string.how_was_the_service,
            value = TipInput,
            onValueChanged = {TipInput = it},
            modifier = Modifier
                .padding(bottom = 32.dp)
                .fillMaxWidth()
)
````
### Add KeyBoard to TextField 

````
@Composable
fun EditNumberField(
 keyboardOptions: KeyboardOptions,
 ){
 TextField(
  keyboardOptions = keyboardOptions
  )
  }
  ````
 It display the number keyboard and next Button

````
  EditNumberField(
   keyboardOptions = KeyboardOptions.Default.copy(
                keyboardType = KeyboardType.Number,
                imeAction = ImeAction.Next),
                )
 ````
  It display the Number keyboard and Done Button

````
EditNumberField(
 keyboardOptions = KeyboardOptions.Default.copy(
                keyboardType = KeyboardType.Number,
                imeAction = ImeAction.Done),
)
````
Password show dot
````
 TextField(
visualTransformation = PasswordVisualTransformation(),
)
````
