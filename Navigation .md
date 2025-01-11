### Navigation to anther Ui 

````
 companion object {
        const val FirstPageRoute = "FirstPage"
        const val HomeRoute = "HomePage"
        const val LoginRoute = "login"
        const val RegisterRoute = "register"
        const val PREF_NAME = "app_prefs"
        const val KEY_FIRST_RUN = "is_first_run"
    }
````

````
NavHost(
    navController = navController, startDestination = FirstPageRoute
) {
    composable(FirstPageRoute) {
        // First Page UI
        // Example: Button to navigate to Login
        Button(onClick = { navController.navigate(LoginRoute) }) {
            Text("Go to Login")
        }
    }
    composable(LoginRoute) {
        // Login Page UI
        // Example: Button to navigate to Register
        Button(onClick = { navController.navigate(RegisterRoute) }) {
            Text("Go to Register")
        }
    }
    composable(RegisterRoute) {
        // Register Page UI
        // Example: Button to navigate to Home
        Button(onClick = { navController.navigate(HomeRoute) }) {
            Text("Go to Home")
        }
    }
    composable(HomeRoute) {
        // Home Page UI
        // Example: Display home content
        Text("Welcome to Home Page")
    }
}

````
### 
 when a note cliked pass a value to other function 
 ````
NavHost(navController = navController, startDestination = "main") {
        // Main screen route
        composable("main") {
            MainContent(navController)
        }
        // Edit note route
        composable(
            route = "edit_note/{noteId}/{noteTitle}/{noteContent}",
            arguments = listOf(
                navArgument("noteId") { type = NavType.IntType },
                navArgument("noteTitle") { type = NavType.StringType },
                navArgument("noteContent") { type = NavType.StringType }
            )
        ) { backStackEntry ->
            val noteId = backStackEntry.arguments?.getInt("noteId") ?:0
            val noteTitle = backStackEntry.arguments?.getString("noteTitle") ?: ""
            val noteContent = backStackEntry.arguments?.getString("noteContent") ?: ""
            TitleAndContentInputFields(navController, noteId,noteTitle, noteContent)
        }
        // Note input screen route
        composable("note_input") {
            TitleAndContentInputFields(navController)
        }
    }
````
to clicked 

````
modifier = Modifier
   .padding(16.dp)
 .clickable {
val encodedTitle = Uri.encode(note.title)
    val encodedContent = Uri.encode(note.content)
   navController.navigate("edit_note/${note.id}/$encodedTitle/$encodedContent")
     }
````
 
