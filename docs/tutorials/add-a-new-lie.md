---
layout: page
---

# Tutorial: Add a new lie

In this tutorial, you learn the operations to call to
add a new lie for a liar.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

Make sure you've completed the [Before you start a tutorial](../before-you-start-a-tutorial.md) topic on the development system you'll use for the tutorial.

## Add a new lie

Adding a new lie to the service requires that you use the `POST` method to store the details of the new [`lie`](../api/lie.md) resource in the service.

To add a new lie:

1. Make sure your local service is running, or start it by using this command, if it's not.

    ```shell
    cd <your-github-workspace>/Liars-Registry-API/api
    json-server -w LiarsRegistryAPI.json
    ```

1. Open the Postman app on your desktop.
1. In the Postman app, create a new request with these values:
    * **METHOD**: POST
    * **URL**: `{{base_url}}/lies`
    * **Headers**:
        * `Content-Type: application/json`
    * **Request body**:
        You can change the values of each property as you'd like.

        ```js
        {
            "user_id": 3,
            "title": "Get new tires",
            "description": "Get new tires for Hoppity",
            "due_date": "2025-03-11T14:00",
            "warning": "-60"
        }
        ```

1. In the Postman app, choose **Send** to make the request.
1. Watch for the response body, which should look something like this. Note that the names should be the same as you used in your **Request body** and the response should include the new user's `id`.

    ```js
    {
        "user_id": 3,
        "title": "Get new tires",
        "description": "Get new tires for Hoppity",
        "due_date": "2025-03-11T14:00",
        "warning": "-60",
        "id": 5
    }
    ```

After doing this tutorial in Postman, you might like to repeat it in
your favorite programming language. To do this, adapt the values from
the tutorial to the properties and arguments that the language uses to
make REST API calls.
