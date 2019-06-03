# Wordpress snippet

## Change logo on login form
```PHP
function change_login_logo()
{
    ?>
    <style type="text/css">
        body.login div#login h1 a {
            background-image: url(<?=get_template_directory_uri(); ?>/images/common/logo.png); //Your logo url here
            padding-bottom: 30px;
        }
    </style>
    <?php
}

add_action('login_enqueue_scripts', 'change_login_logo');
```

## Change logo link on login form

```PHP
function login_url()
{
    return home_url(); //Link to home page
}

add_filter('login_headerurl', 'login_url');
```

## Change logo title on login form
```PHP
function login_title()
{
    return get_option('blogname');
}

add_filter('login_headertitle', 'login_title');
```
