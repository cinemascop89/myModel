# MyModel

A light ActiveRecord ORM for the PHP programmer.

## Installation
To install, only copy the folder to a folder on your project folder.

## Configuration
To override the default configuration, use the Model::$config array
with th following fields:

    db.host     server of the database
    db.name     database name
    db.user     user name
    db.password user password

## Usage
Use is also dead simple,
assuming you have a table 'users' with fields 'name' and 'age':

Declaring a model:

    require_once 'model.php'

    class User extends Model {
    }


Creating and saving instances:

    $user = new User();
    $user->name = 'John Doe';
    $user->age = 22;
    $user->save();

Using relations:

If you have a table called followers, with a field 'user_id', 
you can get an array of followers that belongs to a given user

    $followers = $user->followers;

Retrieving records:

    $myGeneration = User::find(array('age' => 22));

    $all = Model::find('User', 'all');

    $me = Model::get('User', array('name'=>'John Doe'));

## Licensing
myModel is public domain, you can do whatever you like with it, 
but I'd love to hear about you if you find it useful in some way.
