# Drawer widget





29.  Now, we will add a Drawer widget that helps us to navigate to another screen for example navigate to the About page that we have inside the pages folder.

<img src="https://lh5.googleusercontent.com/SHxVAkbmOBRb4QPfHg7Ee4lstjWl_V6SgNGRfbD91pMUaqYxl8HrexQIWfwiTWHxdHP4j3ofwhrWu4vizoKo2qZ50ea166O6-7b3RicjKmJLGUR3fgtbyrXDzUyHeU_C2SRBfzKV" alt="img" width="250" />   <img src="https://lh6.googleusercontent.com/D_ODR5A70n2RarvlPALmK_A3V6t6m7dnZiOnfcWzTfJJjS0NicmV6JuTjbZ55Z8z03LokN2ygKxD8Uq8hZRH_tBMKoWfjgAZQZZrvpMxBJXtuC0lSf_j99wTSff4G9XWjoUhG7mE" alt="img" width="250" />



30. To add a **Drawer** widget; first, create a new folder inside the “**lib**” folder, and name it "**widgets**", and this folder will hold the shared widgets.

<img src="https://lh4.googleusercontent.com/szjmtfxnJ1-R9GkohfVGshm2GZbBNnqj0HghIqG6it3wHDvQTUpn1rbCiTlCQqTIQ0DzUuL3M3yz_L4N2P3HQ4r8UzadlcIgcO1rbTGHo_ejQ0AsAT8Mr3zYKawg3T1L9ZM4vtNQ" alt="img" width="250" />




31. Then, create a new dart file inside the "**widgets**" folder, and name it **“custom_drawer.dart”**.

<img src="https://lh5.googleusercontent.com/_dm8RXd6RCqX7ELuxlVWbDsROhFfzAAXh6cIT3NfI6_u9NrE_rN8fSq0fnyEZh3cEacw0tysi9W7HGUZKOG-2M1mldrBrlwILUAnM5YHc6vNtK9xAkUlZ7LB_tYTBq_HBhmr0mHv" alt="img" width="250" />

​				




32. Create a new stateless widget, and name it **CustomDrawer**.

```dart
class CustomDrawer extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container();
  }
}
```

> Don’t forget to import the **material.dart** file





33. Replace the **Container** widget with the **Drawer** widget.

<img src="https://lh6.googleusercontent.com/a8nCIl-TpHPqATpDs2S70M3BxVDVkBhIT_NvuIq5bTlJhnknW0pwJBLhbLA44Q7dLnUm5lGwYvXGnqpWtG9MgQKhxV0kwbzMDstnQSeVMoLXThI6L3WZTP9u9RZAXCQsuLRjBgAi" alt="img" width="250" />

```dart
class CustomDrawer extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Drawer();
  }
}
```



34. Then inside the **Drawer** widget use the **child** named argument and add the **Column** widget. Here we used the **Column** widget because we want to add two buttons from top to down; one for the **Home** page, and the other for the **About** app page.

<img src="https://lh4.googleusercontent.com/NvPbNPTaqR-ZJcUL_BksXzor0hrLLFNdHUYel6uEcBYLNPruMgvstYVVwouUcDbJepF3jlva6xdu-rs6uNDVJJ8e-NdpaFZdS2BmChBrOoGYxpmnVb2I3gUUz8MX59y0JEgw-v9w" alt="img" width="250" />

```dart
class CustomDrawer extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Drawer(
      child: Column(
        children: [
          
        ],
      ),
    );
  }
}
```





35. Inside the **children** named argument, we will use two **ListTile** widgets.

```dart
class CustomDrawer extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Drawer(
      child: Column(
        children: [
          // Home Page
          ListTile(
            onTap: () {},
            leading: Icon(
              Icons.home,
              size: 40,
              color: Colors.blue,
            ),
            title: Text(
              'Home',
              style: TextStyle(
                fontSize: 24,
                fontWeight: FontWeight.bold,
              ),
            ),
          ),

          // About App Page
          ListTile(
            onTap: () {},
            leading: Icon(
              Icons.info,
              size: 40,
              color: Colors.blue,
            ),
            title: Text(
              'About APP',
              style: TextStyle(
                fontSize: 24,
                fontWeight: FontWeight.bold,
              ),
            ),
          ),
        ],
      ),
    );
  }
}
```



36. Now, we developed our Custom Drawer widget, let's use it. We will call this widget inside the **HomePage** and **AboutPage** widgets. Go to the **home_page.dart**, and import the **custom_drawer.dart** file.

```dart
import '../widgets/custom_drawer.dart';
```



37. Then go down to the **Scaffold** widget, and use the drawer named argument, and inside this named argument call the **CustomDrawer()** widget.

<img src="https://lh3.googleusercontent.com/tMJN8Q0WNShgz7eWoIZS0Xynec13J8Gnh6SE23Zinen-qrq6abqHiLnLQ9FwYprq2d3DLSfzKDCRAKep1qPW1PgKkPXBvFgAxzwDnnISc6iIwcgnkYfdcgSgDf8q5dJkewvF37N7" alt="img" width="350" />





38. Save the file, and you will see the **Drawer** widget on your home page widget.

<img src="https://lh6.googleusercontent.com/z1i_6JY_end25Hu1Xh7hvZMWFC7-s739llkMjPGIA9MAjuQwoam_wd7FzztBWqykfwl9-1GnpCTomg7NAVSm6gJzvz6tkD-VPvpAf3ZrxJnJBPJ9kvwgwZCphXc7xaMDwirV4coh" alt="img" width="350" />





39. Click this **Menu** icon, and you will see your **CustomDrawer** widget.

<img src="https://lh6.googleusercontent.com/6OcKNLDapn_V1O_yGpBuZEIlzevuzX3Vu3PoJyPMdoyYXUAXk57yuq4A88An6YA7TKwo6VN3hHApV84prmBDzA8oyjnHsRHl46Wlm-_dm-DJ78vtD_5PDqFiP4b38ihBBugRDY4r" alt="img" width="350" />





There is one issue, which is your **ListTile** widget, takes the space at top of the phone screen.





40. To fix this problem, go to the **custom_drawer.dart** file, and wrap the **Column** widget with the **SafeArea** widget.

<img src="https://lh3.googleusercontent.com/unk4oen499Z-la8uRqMY0VeK6d-fZoMF4O0tt1qZuTCzAStNJ2uxOuoDqpUhZIoe99i7_rlpLKLkiQgwykJ3HaSu-Vrxq27h0oiAy_3al8E7Kz6Xrwlnf0H2lIVlkvfnLEmJyug3" alt="img" width="550" />


```dart
class CustomDrawer extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Drawer(
      child: SafeArea(
        child: Column(
          children: [
            // Home Page
            ListTile(
              onTap: () {},
              leading: Icon(
                Icons.home,
                size: 40,
                color: Colors.blue,
              ),
              title: Text(
                'Home',
                style: TextStyle(
                  fontSize: 24,
                  fontWeight: FontWeight.bold,
                ),
              ),
            ),

            // About App Page
            ListTile(
              onTap: () {},
              leading: Icon(
                Icons.info,
                size: 40,
                color: Colors.blue,
              ),
              title: Text(
                'About APP',
                style: TextStyle(
                  fontSize: 24,
                  fontWeight: FontWeight.bold,
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```



<img src="https://lh4.googleusercontent.com/X_ZdjKKCSNMe9wVOSVfYc0PliCfpWOtp1y_Og8XFrhQm0ULx37CRt44OIANKPnQGS-kxE5nngflvT7oFMyp7UpiT6VkF7XP30nFu7l3bwWibpDwjQPiKX7WpxiO8bCER1YEJf0Jd" alt="img" width="350" />

>  We fixed this issue ^_^.



41. Now, when you try to click these two **ListTile** widgets, nothing happens; So let's add Navigation logic.

<img src="https://lh4.googleusercontent.com/gthZXr7h86536NcJLU_jgReiGxAnac98MU7DOG_YVkrD2OpZb5FZV9kjMzqW8W006p3Y_3xLtAGJJMy-b5NrBOtVVPqiF91F5r0OMuE0lLzuJNR2RtUMOY-uvRITH_Ith_P9iAWo" alt="img" width="350" />





42. First, import the pages file inside the **custom_drawer.dart** file.

    ```dart
    import '../pages/about_page.dart';
    import '../pages/home_page.dart';
    ```





43.  Use the **Navigator.pushReplacement** method inside the **onTap** named argument in both the **Home ListTile** and **About App ListTile** widgets. Also, do not forget to call the appropriate page for each of the **ListTile** widgets.

    ```dart
    class CustomDrawer extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return Drawer(
          child: SafeArea(
            child: Column(
              children: [
                // Home Page
                ListTile(
                  onTap: () {
                    Navigator.pushReplacement(    // <- Here
                      context,
                      MaterialPageRoute(
                        builder: (context) =>
                            HomePage(), // <- Here, we call the HomePage widget
                      ),
                    );
                  },
                  leading: Icon(
                    Icons.home,
                    size: 40,
                    color: Colors.blue,
                  ),
                  title: Text(
                    'Home',
                    style: TextStyle(
                      fontSize: 24,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                ),
    
                // About App Page
                ListTile(
                  onTap: () {            // <- Here
                    Navigator.pushReplacement(
                      context,
                      MaterialPageRoute(
                        builder: (context) => AboutPage(),  // <- Here, we call the AboutPage widget
                      ),
                    );
                  },
                  leading: Icon(
                    Icons.info,
                    size: 40,
                    color: Colors.blue,
                  ),
                  title: Text(
                    'About APP',
                    style: TextStyle(
                      fontSize: 24,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                ),
              ],
            ),
          ),
        );
      }
    }
    ```

    > **Note:** we used the **pushReplacement()** method instead of the **push()** method because we want to replace the current route of the navigator.







44. Save the file, and try using the Drawer widget to navigate between **Home Page** and **About App** Page.



<img src="https://lh4.googleusercontent.com/UlCxWQLNAPOR1r96HGqGBNVo8XfY4dKsoQZcxsEVMWlhT6OZY54hjSHBTWh9Bo6U8yAV6jQQMBbqdXq-toFCH0wtWelcpJiPFimqpwVqxaWjmnublZ_GCLnuOaJ_kcQVa7ykjZjg" alt="img" width="350" />















