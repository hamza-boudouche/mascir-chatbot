# Elderly-care-chatbot

## Contents

- [Elderly-care-chatbot](#elderly-care-chatbot)
	- [Contents](#contents)
	- [Project description](#project-description)
	- [Architecture](#architecture)
		- [Frontend](#frontend)
		- [Backend](#backend)
	- [Contributing to the project](#contributing-to-the-project)

## Project description

`Elderly-care-chatbot` is an all in one tool whose soul purpose is to help the elderly better communicate with the outside world.

As its name suggests, the primary functionnality of this project is a chatbot through which the elderly user can interact easily with the system, either by voice or text. That means that the chatbot is capable of receiving voice messages from the user and generating voice responses.

## Architecture

The system is meant to have a lot of functionnalities, including by not limited to (new functionnalities can be added as developpement progresses):

- Calendar management
- Web browsing automation
- Video calls management

After a thourought study, we concluded that a microservices based architecture will be best suited for the following reasons:

- Decoupling the different parts of the system is beneficial, because it allows us to have loosly coupled microservices that can be easily updated without affecting the rest of the system
- the different parts of the system often need to meet different standards and are subject to different constraints and work loads, therefore we must be able to scale each part individually
- this type of architecture give the developpers more flexibility regarding the implementation of the system, as every microservice can be implemented in different programming languages and environnement than the others.

Moreover, it was concluded with agreement with the project manager that the system will be a web application, meaning that it will be necessary to divide the architecture into 2 parts: a frontend part and a backend, communicating through some protocol (HTTP, sockets ...)

Finally, the agreed upon architecture is as follows:

&rarr; TODO: make an architectural diagram

### Frontend

As explained above, the system offers many functionalities, beyond the simple chatbot interaction, like calendar management, automated web browsing, and video calls management. Although these services are seperate from the chatbot service, the only way the user is intended to use them is by chat. Therefore the application's frontend interface will be very simple, resembling to popular chat interfaces, like Whatsapp or Facebook Messaenger.

&rarr; TODO: add frontend screenshot

### Backend

The backend side must follow the microservices pattern, therefore each set of related functionalities that can function individually and in a isolated manner should constitute a microservice. Refer to the architectural diagram for details.

## Contributing to the project

In order to contribute to this project, create a branch with a descriptif name of the functionality you want to add. Upon completion open a pull request to merge that branch to `main`. Once merged, an action will be trigered, to run automated tests and generate docker images of the different microservices.
