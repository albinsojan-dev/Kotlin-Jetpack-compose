### Add support for landscape orientation

````
   Column(
        modifier = Modifier
            .padding(40.dp)
            .verticalScroll(rememberScrollState()),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {
        //...
    }
````
Import the following:

````
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.verticalScroll
