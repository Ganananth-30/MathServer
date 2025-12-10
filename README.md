# Ex.04 Design a Website for Server Side Processing
## Date: 10-12-2025

## AIM:
To create a web page to calculate vehicle mileage and fuel efficiency using server-side scripts.

## FORMULA:
M = D / F
<br> M --> Mileage (in km/l)
<br> D --> Distance Travelled (in km)
<br> F --> Fuel Consumed (in l)

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM:
```

math.html

<html>
<head>
    <title>Mileage Calculator</title>
    <style>
        body 
        {
            background: linear-gradient(lime,yellow);
        }
        .id1 
        {
            text-align: center;
            color: brown;
             
        }
        .box 
        {
            text-align: center;
            width: 30%;
            background-color:cyan;
            border: solid 8px gold;
            padding: 50px;
            margin: 90px auto;
        }
        .result 
        {
            margin-top: 20px;
            font-weight: bold;
        }
        h4
        {
        text-align: center;
        }
    </style>
</head>
<body>
    <div class="box">
        
        <form method="post">
        <h1 class="id1">The Mileage Calculator</h1>

            {% csrf_token %}<br>

            <label>Distance Travelled </label>
            <input type="number" name="distance">(km)<br><br>

            <label>Liters Consumed</label>
            <input type="number" name="liters">(L)<br><br>

            <button type="submit">Calculate</button>
            <br>
            <br>
             <label>Mileage</label>
            <br>
            <input class='result' type="number" name="Mileage" value={{miles}}>Km/L

        </form>
    </div>
<h4> GANANANTH.H  (25010984)</h4>
</body>
</html>


views.py


from django.shortcuts import render
def miles(request):
    km = int(request.POST.get('distance', 0))
    l = int(request.POST.get('liters', 0))
    miles = km / l if request.method == 'POST' and l != 0 else 0
    print("kilometers =", km)
    print("liters =", l)
    print("Mileage =", miles)
    return render(request, 'mathapp/math.html', {'km': km, 'l': l, 'miles': miles})


url.py

from django.urls import path
from mathapp import views

urlpatterns = [
    path('', views.miles, name='miles'),
]


```
## OUTPUT - SERVER SIDE:
![alt text](<Screenshot (25).png>)

## OUTPUT - WEBPAGE:
![alt text](<Screenshot (24).png>)

## RESULT:
The a web page to calculate vehicle mileage and fuel efficiency using server-side scripts is created successfully.
