# Beginners-FLASK-TUTORIAL
basicl python flask project-python code ,html tag full detailes inside
http://127.0.0.1:5000/

python code:
from flask import Flask,render_template,request
app=Flask(__name__)
@app.route('/')
def home():
    return  render_template('Register Page.html')

@app.route("/finalpage.html",methods=['POST','GET'])
def Register():
    if request.method == 'POST':
        n=request.form.get("Name")
        a=request.form.get("Age")
        c=request.form.get("City")
        m=request.form.get("Mobile")
        e=request.form.get("Email")
        return render_template("finalpage.html",Name=n,Age=a,City=c,Mobile =m,Email=e)

if __name__=="__main__":
    app.run(debug=True)
    
    
    
    html code
    
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Registration</title>
</head>
<body>

<h1>Hi My Dear Python Developers </h1>
<h2>Welcome to Myfirst flask webpage</h2>
<h3>Kindly Join our MyWebpage</h3>

<form action="finalpage.html" method="post">
    <label>Name</label>
    <input type="text" name="Name">
    <label>Age</label>
    <input type="text" name="Age">
    <label>city</label>
    <input type="text" name="City">
    <label>Mobile</label>
    <input type="text" name="Mobile">
    <label>Email</label>
    <input type="text" name="Email">

        <input type="submit" value="Join Guys">

</form>
</body>
</html>



html final page code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Register Success</title>
</head>
<body>
<h3>Registration Success</h3>
<h4>Thanks for joining</h4>
<table>
     <tr>
       <td>Name</td><td>{{Name}}</td>
     </tr>

  <tr>
       <td>Age</td><td>{{Age}}</td>
     </tr>

  <tr>
       <td>City</td><td>{{City}}</td>
     </tr>

  <tr>
       <td>Mobile</td><td>{{Mobile}}</td>
     </tr>

  <tr>
         <td>Email</td><td>{{Email}}</td>
     </tr>

</table>
</body>
</html>
