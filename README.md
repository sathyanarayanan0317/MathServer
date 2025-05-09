# Ex.05 Design a Website for Server Side Processing
## Date:09.05.2025

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

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

## PROGRAM :
```
<html>
    <head>
        <script type="text/javascript">
            function check()
            {
                var x=Number(document.getElementById("ans1").value);
                var y=Number(document.getElementById("ans2").value);
                var ans5=x*x*y;
                document.getElementById("ans4").value=ans5
            }

        </script>
        <style>
            input{
                display: block;
                margin-left: auto;
                margin-right: auto;
                width: 300px;
                padding-left: 20px;
                padding-right: 20px;
                padding-bottom: 8px;
                padding-top: 8px;
                border: 2px solid #e2d7d7;
                border-radius: 10px;
                background-color: rgba(255, 255, 255, 0.3);
            
            }
            
            h2{
                text-align: center;
                font-size: 1.7rem;
                font-weight: bold;
                
            }
            
            div{
                width: 400px;
                margin-top: 100px;
                margin-left: auto;
                margin-right: auto;
                padding: 40px;
                border: 2px solid #e2d7d7 ;
                border-radius: 40px;
                background-color: rgba(255, 255, 255, 0.1);
            }
            img{
                width: 100px;
                margin-left: auto;
                margin-right: auto;
                display: block;
                border-radius: 49px;
                border: 2px solid #e2d7d7 ;
            
            }
            body{
                background-image: url("https://4kwallpapers.com/images/walls/thumbs_3t/19672.jpg");
                background-size: cover;
            }
            
            input::placeholder {
                color: #1d1818;
            
            }
            
            .dif{
                width: 100px;
                margin-top: 20px;
                cursor: pointer;
            }
        </style>
    </head>
    <body>
        <div>
            <br><h2>Intensity</h2><br> 
            <input type="text" placeholder="enter the intensity" id="ans1">
            <br><h2>Resistance</h2><br>
            <input type="text" placeholder="enter the resistance" id="ans2">
            <input  class="dif" type="button" onclick="check();" value="GO">
            <br><h2>Power</h2><br>
            <input type="text" id="ans4" value="">
        </div>
    </body>
</html>

viwes.py
from django.shortcuts import render
def surfacearea(request):
    context={}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        r = request.POST.get('radius','0')
        h = request.POST.get('height','0')
        print('request=',request)
        print('radius=',r)
        print('height=',h)
        area = 2 * 3.14 * int(r) * int(h) + 2 * 3.14 * int(r) * int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area=',area)
    return render(request,'mathapp/math.html',context)

urls.py
from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfaceareaofcylinder/',views.surfacearea,name="surfaceareaofcylinder"),
    path('',views.surfacearea,name="surfaceareaofcylinderroot")
]
````


## SERVER SIDE PROCESSING:

![image](https://github.com/user-attachments/assets/8045f074-202e-41b5-8aa3-070a8289e2e6)


## HOMEPAGE:
![image](https://github.com/user-attachments/assets/7df7bacc-cdd0-4253-b56d-7dbf25be7fd6)



## RESULT:
The program for performing server side processing is completed successfully.
