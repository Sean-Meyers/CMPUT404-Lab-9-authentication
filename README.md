# authentication-lab

University of Alberta, CMPUT 404 Lab 9 starter repository. Use the different
HTTP authentication schemes provided in Django Rest Framework.

## Getting Started

1. Clone this repository.
    * `git clone https://github.com/uofa-cmput404/authentication-lab.git`
2. Change directory into this repository.
    * `cd authentication-lab`
3. Initialize a Python3 virtual environment
    * `virtualenv venv --python=python3`
4. Activate the virtual environment and install the application dependencies
    ```bash
    source venv/bin/activate
    pip install -r requirements.txt
    ```
5. Run the migrations and create a superuser.
    ```bash
    ./manage.py migrate
    ./manage.py createsuperuser
    ```
6. Start the Django application.
    `./manage.py runserver`

**Question 1:** What authentication scheme is used by default in Django Rest Framework's browsable API? How is this managed?
- BasicAuthentication and SessionAuthentication are used, and they can be changed in the settings.py file in the DEFAULT_AUTHENTICATION_CLASSES entry of the REST_FRAMEWORK dict.

**Question 2:** What authentication scheme is used by httpie when querying with the -a or --auth option flag?
- basic is used: https://httpie.io/docs/cli/authentication

**Question 3:** What is the difference between Session Authentication and Token Authentication? How is Token Authentication an improvement over Basic Authentication?
- In Session Authentication, the user is authenticated for a certain duration. The authentication info is stored on the server and the session ID is sent back and forth between the user and the server. In Token Authentication, the server generates a token based on a secret key, which is stored by the user, who will then send it to the server when they make their requests, the server can decrypt the token with the secret key to verify the validity of the request. Since with basic auth, it is possible for a user to choose a simple password and not change it very very often, it is possible for an aggressor to guess the password or intercept it and potentially use it for a long time, whereas with token based, it is much harder to guess and is unlikely to be valid for very long.

**Question 4:** Provide a high level summary of what happens during an OAuth2 authentication flow. For instance: bitbucket.org > Log In > Log in with Google. What happens when I click "Log in with Google"?
- Bitbucket sends me an authorization request, I then send an authorization grant to bitbucket, bitbucket then forwards the authorization grant to goole, who then send an access token to bitbucket, who then sends the access token to the resource server, which then sends the protected resource to bitbucket. ?

**Question 5:** Please provide a link to your code.
- what code?? All I did was change settings.py.
- https://github.com/Sean-Meyers/CMPUT404-Lab-9-authentication