### Switch

````
var roundUp by remember { mutableStateOf(false) }
````
````
@Composable
fun RoundTheTipRow(
    roundUp:Boolean,
    onRoundUpChanged:(Boolean) -> Unit,
    modifier : Modifier = Modifier){

    Row(
        modifier = modifier
            .fillMaxWidth()
            .size(48.dp),
        verticalAlignment = Alignment.CenterVertically
    ) {
        Text(
            text = stringResource(R.string.round_up_tip)
        )
        Switch(
            modifier = modifier
                .fillMaxWidth()
                .wrapContentWidth(align = Alignment.End),
            checked = roundUp ,
            onCheckedChange = onRoundUpChanged,
            )
    }
}

````
````
 Column(
        
          
    ) {
        RoundTheTipRow(
            roundUp = roundUp ,
            onRoundUpChanged ={roundUp = it},
            modifier = Modifier
                .padding(bottom = 32.dp)
        )
       }
