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


