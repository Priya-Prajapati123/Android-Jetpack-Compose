# Android-Jetpack-Compose
package com.example.jetpackcomposetutorial
import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.jetpackcomposetutorial.ui.theme.JetpackComposeTutorialTheme


class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        setContent {
            JetpackComposeTutorialTheme {
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    GreetingImage(
                        name = "Jetpack Compose Tutorial",
                        message = "Jetpack Compose is a modern toolkit for building native Android UI. Compose simplifies and accelerates UI development on Android with less code, powerful tools, and intuitive Kotlin APIs.",
                        message1 = "In this tutorial, you build a simple UI component with declarative functions. You call Compose functions to say what elements you want and the Compose compiler does the rest. Compose is built around Composable functions. These functions let you define your app\\'s UI programmatically because they let you describe how it should look and provide data dependencies, rather than focus on the process of the UI\\'s construction, such as initializing an element and then attaching it to a parent. To create a Composable function, you add the @Composable annotation to the function name",
                        modifier = Modifier
                            .padding()
                    )

                }

            }
        }
    }

    @Composable
    fun GreetingText(
        name: String,
        message: String,
        message1: String,
        modifier: Modifier = Modifier
    ) {
        Column(
            verticalArrangement = Arrangement.Center,
            modifier = modifier.padding(2.dp)
        ) {

        }
    }

    @Composable
    fun GreetingImage(name: String, message:String,message1:String,modifier: Modifier = Modifier) {
        R.drawable.bg_compose_background
        Column(modifier = modifier.padding(2.dp)) {
            val image = painterResource(R.drawable.bg_compose_background)
            Image(
                painter = image,
                contentDescription = null,
                contentScale = ContentScale.FillWidth
            )

            Text(
                text = name,
                fontSize = 24.sp,
                modifier = modifier.padding(16.dp)
            )

            Text(
                text = message,
                fontSize = 12.sp,
                textAlign = TextAlign.Justify,

                )
            Text(
                text = message1,
                fontSize = 12.sp,
                textAlign = TextAlign.Justify
            )
        }
    }

    @Preview(showBackground = true)
    @Composable
    fun GreetingPreview() {
        JetpackComposeTutorialTheme {
            GreetingText(
                name = "Jetpack Compose Tutorial",
                message = "Jetpack Compose is a modern toolkit for building native Android UI.Compose simplifies and accelerates UI development on Android with less code, powerful tools, and intuitive Kotlin APIs.",
                message1 = "In this tutorial, you build a simple UI component with declarative functions. You call Compose functions to say what elements you want and the Compose compiler does the rest. Compose is built around Composable functions. These functions let you define your app\\'s UI programmatically because they let you describe how it should look and provide data dependencies, rather than focus on the process of the UI's construction, such as initializing an element and then attaching it to a parent. To create a Composable function, you add the @Composable annotation to the function name."
            )
        }
    }
}

