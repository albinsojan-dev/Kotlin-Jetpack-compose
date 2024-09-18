### Click icon next page in jetpack compose
````
 fun NavController() {
        val navController = rememberNavController()
        NavHost(navController = navController, startDestination = "first_screen") {
            composable("first_screen") {
                ClockComposable(navController = navController)
            }
            composable("second_screen") {
                // Second screen screen
                SecondScreen()
            }
        }
    }
````
````
  // Second screen
    fun SecondScreen() {
        // Call the switch button
        SettingButton().SwitchWithCallback()
    }
````
````
Button(
        // Navigate to second screen when setting button is clicked
           onClick = { navController.navigate("second_screen") },
           colors = ButtonDefaults.buttonColors(
           containerColor = Color.White, // Background color when the button is enabled
            contentColor = Color.White, // Content (text) color when the button is enabled
           disabledContainerColor = Color.Red, // Background color when the button is disabled
          disabledContentColor = Color.Red // Content (text) color when the button is disabled
   ),
         modifier = Modifier.padding(16.dp)
                    ) {
          Icon(
         // Setting button icon
         painter = painterResource(id = R.drawable.baseline_settings_24),
         contentDescription = "Settings Icon",
         tint = Color.Black // Color of the icon
 )
                    }
