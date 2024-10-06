# Different types of renderers

**Introduction**

Renderers are the core classes in DRF that display the API output in different formats like JSON and XML. You’ve already
learned how to use the Browsable API renderer, JSON renderer, and a third-party renderer called XMLRenderer. In this
reading, you are going to learn about a few other useful renderers that you can use in your API projects in DRF.

**TemplateHTMLRenderer**

Sometimes, even in an API project, it might be required to display HTML output. For example, if you generate an
invoicing API, you need to display the transaction and order details in a nicely formatted way using HTML and CSS. In
such cases, DRF’s _TemplateHTMLRenderer_ can help.

**Step 1**

Using the _TemplateHTMLRenderer_, you can pass the data to an HTML file and then display that data using Django’s native
templating language called DTL, or Django Templating Language.

To test this _TemplateHTMLRenderer_ the menu items need to be displayed in an HTML file instead of JSON. To use this
renderer, you first import it from the _rest_framework.renderers_ module in the **views.py** file. You also need to
import the _renderer_classes decorator_.

1

2

**Step 2**

The second step is to create a new function called menu in the **views.py** file.

6

Note how the serialized data is passed as context to the HTML template file named _menu-items.html._ You need to put
this HTML file inside the templates directory in your Django app, so the path of this file is:
_LittleLemon/LittleLemonAPI/templates/menu-item.html_

**Step 3**

The third step is to add the following templating code to this HTML file. This code block accepts the template data and
displays them in a HTML table.

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

**Step 4**

The final step is to map this function to an API endpoint in the urls.py file so that it can be browsed as
_http://127.0.0.1:8000/api/menu_.

3

4

5

6

7

Now the _http://127.0.0.1:8000/api/menu_ API endpoint displays all the menu items in a nicely formatted HTML table.

[//]: # (![Menu-items endpoint displays menu items in formatted HTML table]&#40;file:///C:/Users/zak/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png&#41;)

**StaticHTMLRenderer**

You can use the _StaticHTMLRenderer_ if any of your API endpoints need to display some HTML content without using any
DTL code inside an HTML file.

**Step 1**

The first step is to import the _StaticHTMLRenderer_ class and _renderer_classes_ decorator like before.

1

2

**Step 2**

Then you need to create a new function called welcome in the **views.py** file.

3

4

5

**Step 3**

The final step is to map this endpoint to an API endpoint. This time, you want to display this message whenever someone
visits the endpoint _http://127.0.0.1:8000/api/welcome_. To do this, you need to open the **urls.py** file and add the
following line to the _urlpatterns_ list:

1

This greeting will now display if someone visits this endpoint.

[//]: # (![Welcome to the Little Lemon API Project greeting]&#40;file:///C:/Users/zak/AppData/Local/Temp/msohtmlclip1/01/clip_image003.png&#41;)

**CSV renderer**

CSV, or comma-separated values, is another popular format used by API developers. Unlike JSON or XML, every field in a
database record is displayed separated by a comma and every record is on a new line.

**Step 1**

DRF doesn’t come with a CSV renderer class by default. So the first step is to install a popular third-party package
using pipenv.

1

**Step 2**

Import this renderer in the **views.py** file.

1

**Step 3**

Add the renderer using the _renderer_classes_ decorator to convert an API endpoint to display CSV instead of JSON. Add
the following line of code in the _menu-items_ function after the _@api_view()_ decorator:

1

Now if you visit the endpoint _http://127.0.0.1:8000/api/menu-items_ in a REST API client like Insomnia, you’d get the
following output.

[//]: # (![API endpoint output in Insomnia]&#40;file:///C:/Users/zak/AppData/Local/Temp/msohtmlclip1/01/clip_image005.png&#41;)

**YAML renderer**

**Step 1**

To display the output of your APIs in YAML, another popular data format, you need to install the
`djangorestframework-yaml` using pipenv.

1

**Step 2**

To test it with the _menu-items_ function, import this YAML renderer in the **views.py** file.

1

**Step 3**

Pass the _YAMLRenderer_ class inside the _renderer_classes_ decorator, just below the _api_view decorator_ above the
_menu-items_ function.

1

Now if you visit the endpoint _http://127.0.0.1:8000/api/menu-items_ in a REST API client like Insomnia, the menu items
will be visible.

[//]: # (![API endpoint output in Insomnia that displays the menu items]&#40;file:///C:/Users/zak/AppData/Local/Temp/msohtmlclip1/01/clip_image007.png&#41;)

**Global settings**

Instead of importing the CSV and YAML renderer classes individually in the views.py file and then passing them to the
_renderer_classes_ decorator above each function, you can make them available globally in your API project. In this way,
the client can get the desired output with a valid _Accept_ header.

To make these renderers available globally, add the following two lines in the **settings.py** file in the
_DEFAULT_RENDERER_CLASSES_ section.

1

2

This is what the _DEFAULT_RENDERER_CLASSES_ section will be like after adding those two lines.

9

Now the client can send the following _Accept_ headers to receive the API output in their desired format.

| **Response type** | **Request header**         |
|-------------------|----------------------------|
| CSV               | _Accept: text/csv_         |
| YAML              | _Accept: application/yaml_ |

**Conclusion**

In this reading, you have learned how to use different types of renderers in your DRF-based API project to display API
output in different formats. There is a dedicated section on renderers in the DRF documentation, which you can access in
the additional resources of this lesson. It showcases other types of renderers you can use with the Django REST
Framework.