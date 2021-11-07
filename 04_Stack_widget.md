# Stack widget



27. To show the **temperature**, we need to use the **Stack** widget which will help us to overlay several widgets in a simple way. We will use it to add the celsius sign above the temperature number. So replace the **body** named argument with

```dart
// 1
      body: Center(
        // 2
        child: Stack(
          children: [

            // 3
            Text(
              '${widget.temp}',
              style: TextStyle(
                color: Colors.blue,
                fontSize: 120,
                fontWeight: FontWeight.bold,
              ),
            ),

            // 4
            Positioned(
              right: 1,
              child: Text(
                '°',
                style: TextStyle(
                  fontSize: 35,
                  color: Colors.grey,
                  fontWeight: FontWeight.bold,
                ),
              ),
            )
          ],
        ),
      ),
```

1. Here, we used the **Center** widget to keep its child in the center of the screen.
2. We used the **Stack** widget, which will help us to overlay several widgets. 
3. We used the **Text** widget to display the temp that we got from the **HTTP** request.
4. Here, we used the **Positioned** widget to control the position of its child inside the **Stack** widget.



28. Now type the name of any city you want to see its temperature; then click the **search** button.

<img src="https://lh5.googleusercontent.com/le_AU2-_VrjuiCeC_Y7qyuF3EFXgtmkxnkK_UOGvSw6nlAnqEclav7OhVYTRgyzfdrk4nDrPMgmwy6oAMS3bdstPubVlGVOOSzmuvlJvmn9BJw1RXi5IeAjDLfSgb49fG9akDTfw" alt="img" style="zoom:50%;" />







































