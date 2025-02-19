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
Button cliked pass a value and go to next page 
````
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            val navController = rememberNavController()
            AppNavHost(navController)
        }
    }
}

@Composable
fun AppNavHost(navController: NavHostController) {
    NavHost(navController, startDestination = "screenA") {
        composable("screenA") {
            FirstPage(navController)
        }
        composable("screenB/{message}") { backStackEntry ->
            val message = backStackEntry.arguments?.getString("message") ?: ""
            ScreenB(message)
        }
    }
}

@Composable
fun FirstPage(navController: NavHostController) {
    var name by remember { mutableStateOf("") }

    Column(
        verticalArrangement = Arrangement.Center,
        modifier = Modifier
            .fillMaxSize()
            .padding(horizontal = 56.dp)
    ) {
        Text(
            text = "First Page",
            fontSize = 24.sp,
            color = Color.Blue,
            modifier = Modifier.padding(horizontal = 66.dp)
        )

        Spacer(modifier = Modifier.height(16.dp))

        TextField(
            value = name,
            onValueChange = { name = it },
            label = { Text("Enter Name") }
        )

        Spacer(modifier = Modifier.height(16.dp))

        Button(
            onClick = {
                val encodedMessage = URLEncoder.encode(name, StandardCharsets.UTF_8.toString())
                navController.navigate("screenB/$encodedMessage")
            }
        ) {
            Text(
                "Go to Second Page",
                color = Color.Black,
                modifier = Modifier.padding(horizontal = 2.dp)
            )
        }
    }
}

````
````
@Composable
fun ScreenB(message: String) {
    Column(
        verticalArrangement = Arrangement.Center,
        horizontalAlignment = Alignment.CenterHorizontally,
        modifier = Modifier
            .fillMaxSize()
            .padding(horizontal = 66.dp)
    ) {
        Text(
            text = "Second Page",
            fontSize = 24.sp,
            color = Color.Blue
        )
        Spacer(
            modifier = Modifier.height(16.dp)
        )
        Text(
            text = "Your name : $message",
            fontSize = 18.sp
        )
    }
}
     ````   
 
