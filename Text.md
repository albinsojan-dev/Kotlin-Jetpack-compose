### Add Text
````
    Column{
        Text(
            text = stringResource(R.string.name),
            fontSize = 45.sp,
            color = Color.Green,
            modifier = Modifier
                .fillMaxSize()
                .wrapContentSize(Alignment.Center)

        )
    }
}

````
### Add  App screen Top Text
````
@OptIn(ExperimentalMaterial3Api::class)

````
````
 CenterAlignedTopAppBar(
        title = {
            Text(text = "Lemonade",
                fontSize = 20.sp,
                color = Color.Black,
            )
        },
        colors = TopAppBarDefaults.smallTopAppBarColors(
            containerColor = md_theme_dark_surfaceTint
        )
        )
````
### Text Down specs

````
Text(text = stringResource(R.string.tip_amount,"$0.00"),
           style = MaterialTheme.typography.displaySmall
           )
       
          Spacer(modifier = Modifier.height(150.dp) )
````
### show to user output with Text 
tip is the Text
````
Text(text = stringResource(R.string.tip_amount,tip),

`````

