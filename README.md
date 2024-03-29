﻿# jetpack-compose-brazilian-currency-visual-transformation

## This package is for your brasilian application :)

1 - Install jitpack in your project in your (settings.gradle.kts)
```gradle
  dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        maven { url = uri("https://jitpack.io")  } //add me please
    }
}
```

2 - Add jetpack-compose-brazilian-currency-visual-transformation dependency in your build.gradle.app (module app)

```gradle
dependencies {
    implementation("com.github.eliezerBrasilian:jetpack-compose-brazilian-currency-visual-transformation:v1.0.1") //add me  
    //...
}
```

## Preview
https://github.com/eliezerBrasilian/jetpack-compose-brazilian-currency-visual-transformation/assets/93846923/638e9a0d-1b85-4b74-a654-2f80e9b03d2b


## You only need to pass the BrazilianCurrencyVisualTransformation on VisualTransformation as show below in this example

```kotlin
//...
import com.braziliancurrencyvisualtransformation.BrazilianCurrencyVisualTransformation

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MoedaBrasileiraTheme {
                // A surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    var valueInput by remember { mutableStateOf("") }

                    OutlinedTextField(
                        value = valueInput,
                        onValueChange = {
                            valueInput = it
                        },
                        visualTransformation = BrazilianCurrencyVisualTransformation(),
                        keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Number),
                    )
                }
            }
        }
    }
}

```

     


