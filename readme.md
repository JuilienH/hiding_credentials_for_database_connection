# Envrionment variables for hiding credentials used to connect to the database
## Example:
database: postgreSQL
python library used to connect: psycopg2

## Background:
The stem script for psycopg2.coonect is like 
conn=psycopg2.connect(host="real_host_info",user="real_user_name",dbname="real_db_name", password="the_password").

## Purpose:
We want to hide the credential in a shared space, we need to set envrionment variables to store them, and in the code, you just need to get the environment variables to let the system autofill them in.

## Steps: Here is how to do it in the Terminal
1. First, to figure out which shell you are running 

echo $SHELL
It will give an output like this:
/bin/zsh

2. And then use the command export to define the environment variable (KEY) and its actual value that you want to hide eventually

export KEY=value

3. Once this is done, simply type the following and it should return the value you just set

eho $KEY

In the python file storing self-defined functions, we can use connection=psycopg2.connect(**params) 
rather than the full info inside connect().
