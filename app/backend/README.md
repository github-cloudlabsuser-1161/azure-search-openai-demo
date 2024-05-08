# Backend Application

The backend application is built using [Quart](https://quart.palletsprojects.com/), a Python framework for asynchronous web applications. The backend code is stored in the `app/backend` folder.

## File Structure

- `app.py`: This is the main application file. It contains the application setup and route definitions.

## Routes

- `/`: The index route.
- `/redirect`: Empty page recommended for login redirect to work.
- `/favicon.ico`: Route for the favicon.
- `/assets/<path:path>`: Route for serving assets.
- `/content/<path>`: Route for serving content files from blob storage.
- `/ask`: Route for handling POST requests.

## Customizing the Backend

Typically, the primary backend code you'll want to customize is the `app/backend/approaches` folder, which contains the classes powering the Chat and Ask tabs. Each class uses a different RAG (Retrieval Augmented Generation) approach, which include system messages that should be changed to match your data.

## Running the Backend

The backend is deployed using Azure services. The `infra/main.bicep` file contains the configuration for the Azure resources. The backend is run using the command `python3 -m gunicorn main:app`.

For more information on customizing the backend, refer to the [customization guide](../docs/customization.md).