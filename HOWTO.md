# INSTALATION

1. first, you must clone this repository, with `git clone https://github.com/dvrg/flask-adminlte.git`
2. enter directory with 
```bash
$ cd flask-adminlte
```
3. create virtual environtment with 
```bash
$ python3 -m venv venv
``` 
4. activate virtual environtment with 
```bash
$ source venv/bin/activate
```
5. after active, you can install package with pip with 
```bash 
$ pip install -r requirements-dev.txt 
```

# GENERAL SETTINGS

+ You can change the application login title template in `app/base/templates/base_site_auth.html`, and change the `<title>` with you app name.
+ You can change the whole application title template in `app/base/templates/base_site.html`, and change the `<title>` with you app name.

# CHANGE ERROR TEMPLATE

You can change error template in `app/base/templates/errors/`, and change you can find `page_403.html`, `page_404.html` and `page_500.html`. Change the template if you want to modified the template

# CHANGE LOGIN/REGISTER TEMPLATE

You can change login template in `app/base/templates/login/`, and change you can find `login.html` and `register.html`. Change the template if you want to modified the template

# CHANGE BASE SITE TEMPLATE

You can change base template in `app/base/templates/site_template/`, and change you can find several file. Change the template if you want to modified the template


# ADD NEW PAGE

1. Open `app > home > templates`
2. Duplicate `page-blank.html`
3. Rename file with new name of pages

## Thing to chage/add when you create new pages from `page-blank.html`

1. Page Title

```html
{% extends "base_site.html" %} {% block title %} Change Here With New Page
Titile {% endblock title %} {% block stylesheets %}
```

2. Content Header

```html
<!-- Content Header (Page header) -->
<section class="content-header">
  <h1>
    Blank page
    <!-- Change This Line -->
    <small>it all starts here
      <!-- Change This Line --></small>
  </h1>
  <ol class="breadcrumb">
    <li>
      <a href="#"><i class="fa fa-dashboard"></i> Home</a>
    </li>
    <li>
      <a href="#">Examples<!-- Change This Line --></a>
    </li>
    <li class="active">
      Blank page
      <!-- Change This Line -->
    </li>
  </ol>
</section>
```

3. Box Title

```html
<!-- Default box -->
<div class="box">
  <div class="box-header with-border">
    <h3 class="box-title">
      Title
      <!-- Change This Line -->
    </h3>
  </div>
</div>
```

4. Box Body

```html
<div class="box-body">
  You new page content place here!
  <!-- Change This Line -->
</div>
<!-- /.box-body -->
```

5. Box Footer

```html
<div class="box-footer">
  Footer
  <!-- Change This Line -->
</div>
```
6. If need add spesified CSS
```html
{% block stylesheets %}
<!-- Specific CSS goes HERE -->
{% endblock %}
```
6. If need add spesified JS
```html
{% block javascripts %}
<!-- Specific JS goes HERE -->
{% endblock %}
```
7. How to add new static file like css, js, images ?
Point to folder `/app/base/static/assets` and place spesified file in sub folder inside `/app/base/static/assets`. ie: If you want add new image, place image in folde img inside `/app/base/static/assets`

8. How to load static file like css, js, images ?
If you like to call the new image after you add the image in folder `/app/base/static/assets/img`, just call like this `<a href="static/assets/img/filename.jpg">`

9. Add new page to sidebar menu
+ Open `app/base/templates/sidebar.html`
+ Find `<!-- Add new sidebar bellow -->`
+ Copy and paste code already exist form another page on sidebar.html
+ ie : copy from XPath like this
```html
 <li>
    <a href="/xpath"> <i class="fa fa-gear"></i> <span>Xpath</span></a> <!-- change this line 'Xpath' word with new page -->
    <span class="pull-right-container">
        <i class="fa fa-angle-left pull-right"></i>
    </span>
</li>
```
+ if you page name is `new-menu.html`, fill `href` with `new-menu` wthout `.html`
+ if you want to change the icon, change `fa-gear` with font-awesome code. You can look the cheatseat in here http://0.0.0.0:5000/ui-icons