### API Reference

## Getting started
- Base URL : http://http://127.0.0.1:5000/ (this app hosted locally)
- Authentication : Token based authentication protocol is used in this app

## Errors handling
    In errors cases the app returns a json object in this format :
    {
      'success':False,
      'error':404,
      'message':'Not found'
    }

    List of errors codes used in the app : 
    - 404 : Not found
    - 422 : Unprocessable entity
    - 500 : Internal server error

## Endpoints

# POST /register

- General: Register a new user and returns his data  
            with a genearted access token.
- Sample : http://127.0.0.1:8000/api/register

    {
    
    "user": {
    
        "name": "rafali",
        "login": "omaf",
        "email": "rafali@gmail.com",
        "first_name": "osos",
        "num_tel": "0751422572525",
        "adresse": "wall strret",
        "pays": "uk",
        "biographie": "...",
        "role": "user",
        "photo": "images/07.png",
        "updated_at": "2021-06-28T10:56:33.000000Z",
        "created_at": "2021-06-28T10:56:33.000000Z",
        "id": 3
    },
    
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIxIiwianRpIjoiMDNjMWMzNjZlOTg3ZGEyYjZkYTUxNzA5MGJiOGNjMjhkNjEyYzZmM2I2ODNlN2Q4ZWFjZTY0ZjEwMjBhZTZjZTYwNTI4NWJlZmQzZTFmNTciLCJpYXQiOjE2MjQ4Nzc3OTYuODI5NzQ5LCJuYmYiOjE2MjQ4Nzc3OTYuODI5Nzk5LCJleHAiOjE2NTY0MTM3OTYuNDQ5ODE0LCJzdWIiOiIzIiwic2NvcGVzIjpbXX0.tFleJDu46UhKTwGZ15WPxacvhCv47VUoH39A5Nmi6VGemLxJp8SkagFZ4fBQDGnweo5bjuFQjUQ6fxas4NoVnzxdVtPRk_HiSwXfWjADg0zUbh8fgmyLNJo8MIsMbQNgn1ga_n7hhHPflpdWL0gfbEMParWjuUGOquWooynUzxsdaYagtlzUkuydnmzctAT1Dbqtmi5OgpzY4DubBWmjHMJ01jrRKM34WO5PUcF8Ud7hy4nF_nwcEElx98DsT16ZS-d853lQ9y4xhZp02YCwRAZTeXb8AfUSuu4cFP7PBl9LCet8bEBg8ns56DXWySS8ef_X8J0sDAmEaEyIMs2aZI58NqOm-TbIlcfJeWEqJgKGvIC0T3ZJYtX_QQ14ERN3SeQne5P778bd6-zv_4GhDFM505QGz0P5cdbLeuYdCYKJGolkHfd9lcFLHzzALsgzeh7dvtOrMULRayyf3pT6cuZUY1gr_xPoWSFWq4caWDsct-KSFFpfJl6rkTrCnAmaAgEs-a8DsJVc7YfhbUAo5afZH7GAKNj_efxPHP9Ss3jdJVPy_6jYkmMSLrJ5wROjJ3JRG4UgkvAzAvKyxNc_YPRTxSwSVRdbQE9gEPYBZSRGK8OY5AqZXJkwJeqBO2SVgQRC1ksLueqraCeP3YhWoKMjik9FWzF00AtBZhMa15k"
}

# POST /login

- General: Verify the login data and the compte state
            and returns an access token if the data is correct .
- Sample : http://127.0.0.1:8000/api/login
    {
    "user": {
        "id": 3,
        "login": "omaf",
        "name": "rafali",
        "first_name": "osos",
        "email": "rafali@gmail.com",
        "num_tel": "0751422572525",
        "adresse": "wall strret",
        "pays": "uk",
        "biographie": "bidoun",
        "photo": "images/07.png",
        "type": "user",
        "compteState": "active",
        "role": "user",
    },
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIxIiwianRpIjoiMjRlYjk5YzI4NmVkZGZlMDBiY2E0MjMyNGNlZWJjNWVhMmJhOTBjYmM2YzZhZDg1ZDVmNDM5MWE0ZGQ1OTFjZTg0ZDBhYWM4YzEwM2VlYTIiLCJpYXQiOjE2MjQ4ODI2MjkuMTQ0NzM3LCJuYmYiOjE2MjQ4ODI2MjkuMTQ0NzcyLCJleHAiOjE2NTY0MTg2MjguNjg1MDY3LCJzdWIiOiIzIiwic2NvcGVzIjpbXX0.lnpWdU6uZh5RYfkgajsK8IpREbJHdmz1ix8VIx3gMIutCq2kLdlnZ0paslCNOf1wUN9zKgrw_CXyuBwjvyV0oZFEGmUkA9_K_cyg3ZM1WqDOZGTAooT1T3xNOgoKcFjUrhny3C4BxbWEWX9UzPCRr1rSCABCIvUbpFFQMllZ420uxvUIkr_6te9tHCRP82vP95BkMF7sTHY7axUYqEFkvotA_cQmSFy0kyikO_jFxXDyFVIeGaF-X7al9om9-rStbyX3JVl8QFycElvyk_dIBEjazz97Zef9fLEhSU67aBMCHtQMjgHVXEVy2l-q9bruqeIb75tRj2dp7-QJDoMi0TXA50bG_vtq2I7ne-9qPQ4Sh9G_Pr_47yZ735hXd0ee3wxg4X5SXJkNJAbSvyRmAffCAtS9i8eufSONElWyflwpc0Cx6gqlywnT0j5mHhNoAXqKHrS3vQMqmgRJQBjKfzhy2MBKm4inEyLdn-0z2Dw4Qw6-_JibCKXj9Vxu-ppxV-n4bZ3oJhAi8ENfWAJAGaXcNoG5Da6Z8_dpvBBH9-NZgf57uf8hUw1l5nwRzHgQFACCxfj1VIxa7YIRe2blM-CO1aMbdlqNrg3X8XiipaWaep-DJrHyvjLNA1M2EeQMZbZWloVM8GatnjDdyOVI77I_rcZuqvDh0MaKvPK1R5U"
}

# POST /get_current_user

- General: Returns current user data.
- Sample : http://127.0.0.1:8000/api/get_current_user
    "current_user": [
        {
            "id": 1,
            "login": "ayoub78",
            "password": "$2y$10$q5.T0On3sJi6mjzLPYKZlOCc5kHyLwzJDj7lqOck2GuuciggBgR.K",
            "name": "ayoub",
            "first_name": "ayoubino",
            "email": "aybrh@gmail.com",
            "num_tel": "020524557",
            "adresse": "25hay 1",
            "pays": "croitia",
            "biographie": "hakha",
            "photo": "images/05.png",
            "type": "user",
            "compteState": "desactive",
            "role": "user",
            "email_verified_at": null,
            "remember_token": null,
            "created_at": "2021-06-10 13:31:32",
            "updated_at": "2021-06-10 13:31:32"
        }
    ]
}

# POST /Recover_password
- General: Sends new password to user email .
- Sample : http://127.0.0.1:8000/api/Recover_password
    {
    "message": "New password send successfully"
    }

# POST /logging_out

- General: Log the current user out . 
- Sample : curl http://127.0.0.1:5000/questions -X POST -H "Content-Type: application/json" -d "{ \"question\": \"Whose the best cm in the world?\", \"answer\": \"Frenkie de jong\", \"difficulty\": 1, \"category\": \"6\" }"
    {
    "message": "Logged out with success"
    }

# GET /categories

- General: Returns a list of all categories
- Sample : http://127.0.0.1:8000/api/categories
    {
    "Categories": [
        {
            "id": 1,
            "name": "Web Dev",
            "created_at": "2021-06-10T18:44:49.000000Z",
            "updated_at": "2021-06-10T21:11:37.000000Z"
        },
        {
            "id": 2,
            "name": "design",
            "created_at": "2021-06-10T18:46:43.000000Z",
            "updated_at": "2021-06-10T18:46:43.000000Z"
        },
        {
            "id": 4,
            "name": "Mobile",
            "created_at": "2021-06-10T20:46:00.000000Z",
            "updated_at": "2021-06-10T20:46:00.000000Z"
        }
    ],
    "Message": "Retrieved successfully"
}

# GET /categories/<int:id_category>

- General: Returns targeted category using the id passed in URL
- Sample : http://127.0.0.1:8000/api/categories/1
    {
    "Categorie": [
        {
            "id": 1,
            "name": "Web Dev",
            "created_at": "2021-06-10 18:44:49",
            "updated_at": "2021-06-10 21:11:37"
        }
    ],
    "Message": "Retrieved successfully"
}

# POST /categories

- General: Creates a new category and returns its data  
- Sample : http://127.0.0.1:8000/api/categories
    {
    "Categorie": {
        "name": "cloud",
        "updated_at": "2021-06-28T13:32:08.000000Z",
        "created_at": "2021-06-28T13:32:08.000000Z",
        "id": 5
    },
    "Message": "Created successfully"
}

# PATCH /categories/<int:id_category>

- General: Updates the targeted category and returns the updated data  
- Sample : http://127.0.0.1:8000/api/categories/1
    {
    "Categorie": {
        "id": 1,
        "name": "Web devs",
        "created_at": "2021-06-10T18:44:49.000000Z",
        "updated_at": "2021-06-28T13:41:00.000000Z"
    },
    "message": "Updated successfully"
}

# DELETE /categories/<int:id_category>

- General: Deletes the targeted category 
- Sample : http://127.0.0.1:8000/api/categories/3
    {
    "Message": "Categorie Deleted succuessfully"
    }

# GET /clients

- General: Returns a list of all clients
- Sample : http://127.0.0.1:8000/api/clients
    {
    "Clients": [
        {
            "id": 2,
            "societe": "Ocp",
            "EstActif": 1,
            "Verified": 0,
            "type": "Holding",
            "rating": "4",
            "user_id": 1,
            "created_at": null,
            "updated_at": null,
            "name": "ayoub",
            "first_name": "ayoubino",
            "email": "aybrh@gmail.com",
            "num_tel": "020524557",
            "adresse": "25hay 1",
            "pays": "croitia",
            "biographie": "hakha"
        },
        {
            "id": 3,
            "societe": "Iam",
            "EstActif": 0,
            "Verified": 0,
            "type": "Pms",
            "rating": "1",
            "user_id": 2,
            "created_at": null,
            "updated_at": null,
            "name": "faradi",
            "first_name": "patrick",
            "email": "faradi@gmail.com",
            "num_tel": "075142257",
            "adresse": "freek strret",
            "pays": "usa",
            "biographie": "walo walo"
        }
    ],
    "Message": "Retrieved successfully"
}

# GET /clients/<int:id_client>

- General: Returns targeted client using the id passed in URL
- Sample :http://127.0.0.1:8000/api/clients/2
    {
    "Client": [
        {
            "id": 2,
            "societe": "Ocp",
            "EstActif": 1,
            "Verified": 0,
            "type": "Holding",
            "rating": "4",
            "user_id": 1,
            "created_at": null,
            "updated_at": null,
            "name": "ayoub",
            "first_name": "ayoubino",
            "email": "aybrh@gmail.com",
            "num_tel": "020524557",
            "adresse": "25hay 1",
            "pays": "croitia",
            "biographie": "hakha"
        }
    ],
    "Message": "Retrieved successfully"
}

# POST /clients

- General: Creates a new client and returns his data  
- Sample : http://127.0.0.1:8000/api/clients
    {
    "Client": {
        "user_id": "2",
        "societe": "AfricaTrains",
        "type": "Pme",
        "EstActif": 0,
        "Verified": 0,
        "rating": "0",
        "updated_at": "2021-06-28T13:58:44.000000Z",
        "created_at": "2021-06-28T13:58:44.000000Z",
        "id": 5
    },
    "Message": "Client profile Created successfully"
}

# PATCH /clients/<int:id_client>

- General: Updates the targeted client and returns the updated data  
- Sample : http://127.0.0.1:8000/api/clients/2
    {
    "Clients": {
        "id": 2,
        "societe": "Msis",
        "EstActif": 1,
        "Verified": 0,
        "type": "Infos",
        "rating": "4",
        "user_id": "2",
        "created_at": null,
        "updated_at": "2021-06-28T14:02:55.000000Z"
    },
    "message": "Updated successfully"
}
# DELETE /clients/<int:id_client>

- General: Deletes the targeted client  
- Sample : http://127.0.0.1:8000/api/clients/3
    {
    "Message": "Client Deleted succuessfully"
    }

# GET /freelancers

- General: Returns a list of all freelancers
- Sample : http://127.0.0.1:8000/api/freelancers
    {
    "Freelancers": [
        {
            "id": 1,
            "category": "coding",
            "rating": 4,
            "user_id": 1,
            "created_at": "2021-06-11 11:29:10",
            "updated_at": "2021-06-11 11:29:10",
            "name": "ayoub",
            "first_name": "ayoubino",
            "email": "aybrh@gmail.com",
            "num_tel": "020524557",
            "adresse": "25hay 1",
            "pays": "croitia",
            "biographie": "hakha"
        },
        {
            "id": 2,
            "category": "design",
            "rating": 2,
            "user_id": 2,
            "created_at": "2021-06-11 11:29:28",
            "updated_at": "2021-06-11 11:29:28",
            "name": "faradi",
            "first_name": "patrick",
            "email": "faradi@gmail.com",
            "num_tel": "075142257",
            "adresse": "freek strret",
            "pays": "usa",
            "biographie": "walo walo"
        }
    ],
    "Message": "Retrieved successfully"
}

# GET /freelancers/<int:id_freelancer>

- General: Returns targeted freelancer data using the id passed in URL
- Sample : http://127.0.0.1:8000/api/freelancers/1
    "Freelancer": [
        {
            "id": 1,
            "category": "coding",
            "rating": 4,
            "user_id": 1,
            "created_at": "2021-06-11 11:29:10",
            "updated_at": "2021-06-11 11:29:10",
            "name": "ayoub",
            "first_name": "ayoubino",
            "email": "aybrh@gmail.com",
            "num_tel": "020524557",
            "adresse": "25hay 1",
            "pays": "croitia",
            "biographie": "hakha"
        }
    ],
    "Message": "Retrieved successfully"
}

# POST /freelancers

- General: Creates a new freelancer and returns his data  
- Sample : http://127.0.0.1:8000/api/freelancers
    {
    "Freelancer": {
        "category": "cloud",
        "rating": "4",
        "user_id": "3",
        "updated_at": "2021-06-28T15:06:52.000000Z",
        "created_at": "2021-06-28T15:06:52.000000Z",
        "id": 3
    },
    "Message": "Created successfully"
}

# PATCH /freelancer/<int:id_freelancer>

- General: Updates the targeted freelancer and returns the updated data 
- Sample : http://127.0.0.1:8000/api/freelancers/2
    {
    "freelancer": {
        "id": 2,
        "category": "Motions Graphic",
        "rating": "2",
        "user_id": "2",
        "created_at": "2021-06-11T11:29:28.000000Z",
        "updated_at": "2021-06-28T15:08:50.000000Z"
    },
    "message": "Updated successfully"
}

# GET /get_freelancers_reviews

- General: Returns all freelancers reviews  
- Sample : http://127.0.0.1:8000/api/get_freelancers_reviews
    {
    "freelancers with reviews": [
        {
            "id": 1,
            "category": "coding",
            "rating": 4,
            "user_id": 1,
            "created_at": "2021-06-11T11:29:10.000000Z",
            "updated_at": "2021-06-11T11:29:10.000000Z",
            "reviews": []
        },
        {
            "id": 2,
            "category": "Motions Graphic",
            "rating": 2,
            "user_id": 2,
            "created_at": "2021-06-11T11:29:28.000000Z",
            "updated_at": "2021-06-28T15:08:50.000000Z",
            "reviews": []
        },
        {
            "id": 3,
            "category": "cloud",
            "rating": 4,
            "user_id": 3,
            "created_at": "2021-06-28T15:06:52.000000Z",
            "updated_at": "2021-06-28T15:06:52.000000Z",
            "reviews": []
        }
    ],
    "Message": "Successfully retrieved"
    }

# DELETE /freelancers/<int:id_freelancer>

- General: Deletes the targeted freelancer
- Sample : http://127.0.0.1:8000/api/freelancers/3
    {
    "Message": "Freelance Deleted succuessfully"
    }

#   GET /portfolios

- General: Returns a list of all portflios
- Sample : http://127.0.0.1:8000/api/portfolios
    {
    "portfolios": [
        {
            "id": 1,
            "diplomes": "Emci,It,iSTA",
            "experiences": "NOT YET",
            "projets_realiser": "a lot",
            "freelancer_id": 1,
            "created_at": "2021-06-11T11:31:43.000000Z",
            "updated_at": "2021-06-11T11:31:43.000000Z"
        }
    ],
    "Message": "Retrieved successfully"
    }

# GET /portfolios/<int:id_portfolio>

- General: Returns targeted portfolio data using the id passed in URL
- Sample : http://127.0.0.1:8000/api/portfolios/1
    {
    "Portfolio": [
        {
            "id": 1,
            "diplomes": "Emci,It,iSTA",
            "experiences": "NOT YET",
            "projets_realiser": "a lot",
            "freelancer_id": 1,
            "created_at": "2021-06-11 11:31:43",
            "updated_at": "2021-06-11 11:31:43"
        }
    ],
    "Message": "Retrieved successfully"
    }

# POST /portfolios

- General: Creates a new portfolio and returns its data
- Sample : http://127.0.0.1:8000/api/portfolios
    "Portfolio": {
        "diplomes": "Isgi,It,iSTA",
        "experiences": "years and years",
        "projets_realiser": "uncountable",
        "freelancer_id": "2",
        "updated_at": "2021-06-28T15:23:59.000000Z",
        "created_at": "2021-06-28T15:23:59.000000Z",
        "id": 3
    },
    "Message": "Portfolio Created successfully"
}

# PATCH /portfolios/<int:id_portfolio>

- General:  Updates the targeted portfolio and returns the updated data
- Sample : http://127.0.0.1:8000/api/portfolios/3
    {
    "portfolio": {
        "id": 3,
        "diplomes": "ISGI",
        "experiences": "years and years",
        "projets_realiser": "uncountable",
        "freelancer_id": 2,
        "created_at": "2021-06-28T15:23:59.000000Z",
        "updated_at": "2021-06-28T15:30:28.000000Z"
    },
    "message": "Updated successfully"
}

# DELETE /portfolios/<int:id_portfolio>

- General: Deletes the targeted portfolio
- Sample : http://127.0.0.1:8000/api/portfolios/2
    {
    "Message": "Portfolio Deleted succuessfully"
    }

# GET /posts
- General: Returns a list of all posts
- Sample : http://127.0.0.1:8000/api/posts
    {
    "posts": [
        {
            "title": "Backend developer needed",
            "name": "Web devs",
            "name_projet": "sucessshhhh",
            "description": "easy",
            "presentation": "salamo 3aliko",
            "statut": "In progress"
        },
        {
            "title": "FRONT developer wanted imediately",
            "name": "Mobile",
            "name_projet": "sucessshhhh",
            "description": "easy",
            "presentation": "salamo 3aliko",
            "statut": "In progress"
        }
    ],
    "Message": "Retrieved successfully"
    }

# GET /posts/<int:id_post>

- General: Returns targeted post data using the id passed in URL
- Sample : http://127.0.0.1:8000/api/posts/1
    {
    "post": [
        {
            "title": "Backend developer needed",
            "name": "Web devs",
            "name_projet": "sucessshhhh",
            "description": "easy",
            "presentation": "salamo 3aliko",
            "statut": "In progress"
        }
    ],
    "Message": "Retrieved successfully"
}

# POST /posts

- General: Creates a new post and returns its data
- Sample : http://127.0.0.1:8000/api/posts
    {
    "Post": {
        "title": "FRONT developer wanted imediately",
        "projet_id": "2",
        "category_id": "4",
        "updated_at": "2021-06-28T17:03:45.000000Z",
        "created_at": "2021-06-28T17:03:45.000000Z",
        "id": 3
    },
    "Message": "Post Created successfully"
}

# PATCH /posts/<int:id_post>

- General: Updates the targeted post and returns the updated data
- Sample : http://127.0.0.1:8000/api/posts/1
    {
    "post": {
        "id": 1,
        "title": "Frontend developer wanted imediately",
        "projet_id": "2",
        "category_id": "4",
        "created_at": "2021-06-10T22:46:30.000000Z",
        "updated_at": "2021-06-28T17:09:08.000000Z"
    },
    "message": "Updated successfully"
}

# DELETE /posts/<int:id_post>

- General: Deletes the targeted post
- Sample : http://127.0.0.1:8000/api/posts/3
    {
    "Message": "Post Deleted succuessfully"
    }

# GET /projects

- General: Returns a list of all projects
- Sample : http://127.0.0.1:8000/api/projects
   {
    "projects": [
        {
            "id": 1,
            "name_projet": "test5",
            "categorie": "gghy",
            "description": "easy",
            "presentation": "jjkl",
            "statut": "hhhuy",
            "client_id": 2,
            "created_at": "2021-06-10T22:43:52.000000Z",
            "updated_at": "2021-06-10T22:43:52.000000Z"
        },
        {
            "id": 2,
            "name_projet": "sucessshhhh",
            "categorie": "gghy",
            "description": "easy",
            "presentation": "salamo 3aliko",
            "statut": "In progress",
            "client_id": 3,
            "created_at": "2021-06-10T22:44:37.000000Z",
            "updated_at": "2021-06-10T22:44:37.000000Z"
        }
    ],
    "message": "Retrieved successfully"
}


# GET /projects/<int:id_project>

- General:  Returns targeted project data using the id passed in URL
- Sample : http://127.0.0.1:8000/api/projects/1
    {
    "project": [
        {
            "id": 1,
            "name_projet": "test5",
            "categorie": "gghy",
            "description": "easy",
            "presentation": "jjkl",
            "statut": "hhhuy",
            "client_id": 2,
            "created_at": "2021-06-10 22:43:52",
            "updated_at": "2021-06-10 22:43:52"
        }
    ],
    "message": "Retrieved successfully"
}


# POST /projects

- General: Creates a new project and returns its data
- Sample : http://127.0.0.1:8000/api/projects
    {
    "project": {
        "name_projet": "Albatros",
        "description": "easy",
        "categorie": "cloud",
        "presentation": "a lot",
        "statut": "In progress",
        "client_id": "3",
        "updated_at": "2021-06-28T18:23:27.000000Z",
        "created_at": "2021-06-28T18:23:27.000000Z",
        "id": 3
    },
    "message": "Created successfully"
}

# PATCH /projects/<int:id_project>

- General:  Updates the targeted project and returns the updated data
- Sample : http://127.0.0.1:8000/api/projects/3
    {
    "project": {
        "id": 3,
        "name_projet": "Mission impossible",
        "categorie": "gghy",
        "description": "easy",
        "presentation": "jjkl",
        "statut": "hhhuy",
        "client_id": 3,
        "created_at": "2021-06-28T18:23:27.000000Z",
        "updated_at": "2021-06-28T18:27:39.000000Z"
    },
    "message": "Update successfully"
}

# DELETE /projects/<int:id_project>

- General:  Deletes the targeted project 
- Sample : http://127.0.0.1:8000/api/projects/2
    {
    "message": "Deleted"
    }   

# GET /reclamations

- General:  Returns a list of all reclamations
- Sample : http://127.0.0.1:8000/api/reclamations
    {
    "Reclamations": [
        {
            "id": 1,
            "description": "Copyright violation",
            "date": "2011-12-18 00:00:00",
            "type": "Copyright",
            "post_id": 1,
            "created_at": "2021-06-11T21:42:16.000000Z",
            "updated_at": "2021-06-11T21:42:16.000000Z"
        },
        {
            "id": 2,
            "description": "Seo violation",
            "date": "2021-12-18 00:00:00",
            "type": "Seo",
            "post_id": 1,
            "created_at": "2021-06-11T21:42:37.000000Z",
            "updated_at": "2021-06-11T22:44:13.000000Z"
        }
    ],
    "Message": "Retrieved successfully"
}

# GET /reclamations/<int:id_reclamation>

- General:  Returns targeted reclamation data using the id passed in URL
- Sample : http://127.0.0.1:8000/api/reclamations/1
    {
    "Reclamation": [
        {
            "id": 1,
            "description": "Copyright violation",
            "date": "2011-12-18 00:00:00",
            "type": "Copyright",
            "post_id": 1,
            "created_at": "2021-06-11 21:42:16",
            "updated_at": "2021-06-11 21:42:16"
        }
    ],
    "Message": "Retrieved successfully"
}

# POST /reclamations

- General:  Creates a new reclamation and returns its data
- Sample : http://127.0.0.1:8000/api/reclamations
    {
    "Reclamation": {
        "description": "Site policy violation",
        "date": "2020-12-18",
        "type": "Seo",
        "post_id": "1",
        "updated_at": "2021-06-28T18:40:49.000000Z",
        "created_at": "2021-06-28T18:40:49.000000Z",
        "id": 4
    },
    "Message": "Reclmation Created successfully"
}

# PATCH /reclamations/<int:id_reclamation>

- General:  Updates the targeted reclamation and returns the updated data
- Sample :http://127.0.0.1:8000/api/reclamations/2
    {
    "reclamation": {
        "id": 2,
        "description": "Seo violation",
        "date": "2021-12-18",
        "type": "Seo",
        "post_id": 1,
        "created_at": "2021-06-11T21:42:37.000000Z",
        "updated_at": "2021-06-28T18:42:37.000000Z"
    },
    "message": "Updated successfully"
}

# DELETE /reclamations/<int:id_reclamation>

- General: Deletes the targeted reclamation 
- Sample : http://127.0.0.1:8000/api/reclamations/2
    {
    "Message": "Reclamation Deleted succuessfully"
    }   



## Authors
Ayoub Rhouttais developed the apis part
