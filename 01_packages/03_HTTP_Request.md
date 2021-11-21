# HTTP Request

In our application, we will need a server that will provide us with the temperature of the cities, and the server that we will use is the **weatherstack** website. This website will provide us with the temperature of each city. To communicate with this website, we will use the HTTP request.

![screenshot](https://lh5.googleusercontent.com/5hIWm4QxYPtCEmRPDCwQIEvTm-qE0drQk1Tsb8KugDgkaW2jdPa5J8P5wKJ9D-7QHuEjT3WUG1YvL7l1SVxoT4fZyR0UiqCEPeSlFXBQcjPAcSf9w0MV-hoYQcWIBwMpFLtfDKao)

So we will use the **HTTP** library in order to request the weather for a particular city. While sending the **HTTP** request, we will provide the server with the name of the city, and then the server will fetch the weather of this city from the database; then it will return an HTTP response with a lot of information, but in our case, we will only need the temperature info.

12. The first step, open the https://weatherstack.com website.

13. Click the **SIGN UP FREE** button, and sign up with a new account.

![screenshot](https://lh4.googleusercontent.com/rTk7GeybdAgBiHOSoglFz6oh7lRttyXhGAZ_8E10tdgx55z8tTaw63CD5QHqcmj2NJojECRwXHOPbqRNzWd1Fjx233zY3QoayKXehqFSEXwlxVUD3zeKSg9I11Wp9JGFOlXzrDZP)

14. Choose the **free** plan.
15. Click the **Documentation**.

![screenshot](https://lh5.googleusercontent.com/eQusJNh-urb_Ls2aT5cikyh9o9wyXY_YnroCKQv-LWRxAequ2RoNzW9XHWXWnV0IrCP_5_z6k8qjZKFDCM3J-mv8URrZkG4mknBlDBQXlzn7zGA2vAx7MlpTV4jXfiG0Ik6h2McY)

16. Go down the Getting Started, then click the **Run API** **Request** button

![screenshot](https://lh5.googleusercontent.com/pmj9WPg6czG_jgTIzFeSNCUrEjhF6npyN9gO2b2Kbgdgkqtn-jCpUJqwUz5-DEaxgqZDk7DMqYv8z_tXQA-O9ftX20S-3BttyS36iRSWe3xvy0icN-ECeWLNowiYlN_XgPQjhmLN)

17. This will open a new browser tab, with some information. Go to the end of the link, and change the “**New%20York**” to “**Kuwait**”. You can change this **query** to any city you want ^\_^.

    > **Note:** sometimes you will get an error that tells you that “Your current Subscription Plan does not support HTTPS Encryption”, and to solve it just change the front of the link from **https** to **http**.

18. Here you will find a lot of information about Kuwait City, including the **temperature**, which we will use in the application.

![screenshot](https://lh3.googleusercontent.com/y7mQi9NfDt2udkOYWs4UnFlb29GCEc3mVrRuQtJKdCC5nXLwOZojiX8CMR9WswOQnYVwTJf4k2hXJ7LNKFoH6GZkG4DGqhMkghVxQ02ewbMcQp4zu6sA_7tE9ryMNlDCK-SB-7SA)

![screenshot](https://lh4.googleusercontent.com/o8XT0byGdMvKngC9CGPL0TEq3X6ZV3Bnvjp5FwqyvfKLIwiY2tr4kyUh9fDHLBgo0-31d6DnmePBh5_OrCfyxVfeYbWdJIeVIHcqHnE3MwI0qch2B7N2phAlzDdwXUw7zn2gHO2X)

> The format that the server will give it to us is called **JSON**. In this case, we will use the **jsonDecode** function to convert this format into a usable format.

19. Here we got this information through the browser. We will learn how we can get this information through the **HTTP** package. First, we should consider when we will request information from the **weatherstack** website; In the case of our application, we will request this information when the user provides the name of the city inside the **TextField** widget, and then when the user clicks the search button.

20. Open the **home_page.dart**

21. Since we need to use the **HTTP** package and the **convert** package, we need to import these two packages. So, import these packages.

    ```dart
    import 'dart:convert';

    import 'package:http/http.dart' as http;
    ```

22. Go down to the **TextButton.icon** widget, and change the **onPressed** named argument.

    ```dart
      			 // 1
                 onPressed: () async {

                    // 2
                    try {
                      // 3
                      var url = Uri.parse('your link');

                      // 4
                      var response = await http.get(url);

                      // 5
                      var objBody = jsonDecode(response.body);

                      // 6
                      var temp = objBody['current']['temperature'];

                      // 7
                      if (objBody['success'] == true) {

                      } else {
                             print('Error');
                      }

                      // 8
                    } catch (error) {
                      print(error);
                    }
                  },
    ```

    1. Since the **http.get** method will take a little time to get the information from the **weatherstack** server, we will need to change the **onPressed** function to async-await function, and to change it you just need to add the **async** keyword.
    2. Here we need to use try-catch in order to catch problems like in the case of disconnecting the internet.
    3. The **http.get** method needs the **Uri** object, so here we created a variable, and we added the link that we got in the step 16. Do not forget to change the ‘**your link**’ to the link that you got in step 16.
    4. Here, we used the **http.get** method to communicate with the **weatherstack** server, and we passed the **Uri** object that we created.
    5. we will use the **jsonDecode** function to convert **JSON** format into a usable format (**Map<String, dynamic>**).
    6. Since we have a **Map** type, we can use brackets to get a specific value from it, in our case we got the **temperature** value.
    7. Here we use the if-condition to check whether the request is a success or a failure.
    8. Catch other problems such as disconnecting the internet.

23. We need to change the **city query** to the city that we got from the **TextField** widget; So Change the end of the link from the “**Kuwait**” to **\_textEditingController.text**.

    ```dart
       var url = Uri.parse('http://api.weatherstack.com/current?access_key=[Your KEY]&query=${_textEditingController.text}');

    ```

    > Don't forget to add your KEY

24. With this approach, we will get the temperature from the **weatherstack** website, and we store it inside the **temp** variable. The next step is that we will need to pass this value to the **WeatherPage** widget. The first step is creating a variable on the page you want to transfer data to; In our case, we want to transfer data from the home page to the **weather** page, so we will create the variable inside the movie page (**WeatherPage**).

Under the **WeatherPage** create two variables one for the **city** and the other for the **temperature**. Also, don’t forget to generate the constructor.

```dart
class WeatherPage extends StatefulWidget {
  final String city;       // <- here
  final int temp;         // <- here
  const WeatherPage({
    Key? key,
    required this.city,
    required this.temp,
  }) : super(key: key);

  @override
  _WeatherPageState createState() => _WeatherPageState();
}
```

25. Go to the **home_page.dart**, and under the **if** condition add this line.

    ```dart
    if (objBody['success'] == true) {
                         Navigator.push(
                          context,
                          MaterialPageRoute(builder: (context) {
                            return WeatherPage(
                                city: _textEditingController.text, temp: temp);
                          }),
                        );
                      } else {
                        print('Error');

                      }
    ```

    > Here, we used the **Navigator.push** method to push to the **WeatherPage** widget; Also, we passed the city and temp variables to it.

26. To display the name of the city that we got from the **TextField**, change the value of the **Text** widget that is inside the **AppBar**, to **widget.city**.

    > **Note:** To access to the variables that we created under the **WeatherPage** class; we need to use **widget** object because we used the **StatefulWidget** instated of **StatelessWidget**.

```dart
 appBar: AppBar(
        title: Text(
          widget.city, // <- Here
          style: TextStyle(
            fontWeight: FontWeight.bold,
          ),
        ),
      ),
```
