# Flatapets Lab

There is a new website called Flatapets dedicated to helping pets find new homes, but they need our help! Our job is to implement a React application to help organize their data!

## Setup

1. Run `npm install` in your terminal.
2. Run `npm run server`. This will run your backend on port `4000`.
3. In a new terminal, run `npm start`. This will run your React app on port `5000`.

In our React application, the data about the Pets is in the `db.json` file. This file will mimic an API that follows RESTful conventions.

Make sure to open [http://localhost:4000/pets](http://localhost:4000/pets) in the browser to verify that your backend is working before you proceed!

## What You Already Have

The `App` component holds two children: `Header` and `PetPage`. The `PetPage` component holds three children: `NewPetForm`, `Search` and `PetList`. These components have some starter code in them already. The `PetList` component will render all `Pet` components.

All of the code to style the page has been written for you, meaning that you should be adding to the code rather than editing it; however, if your finished product has some styling issues, don't worry too much about it.

# Core Deliverables

As a user, I should be able to:

- See list of pets on the page, using the `Pet` component. The `Pet` component should display the pet's image, name, and conditionally render whether it is from a pet shop or from the wild. If the pet is from a pet shop, the component should say "From a Pet Shop", otherwise it should say "From the wild".
- Click on the image of the pet in the `Pet` component and see the animal_type in place of the name. If I click on the image again, the animal_type should again be replaced with the name. If I click on another pet's image, it toggles that pet's name independent of any other pet's.
- Submit the form in the `NewPetForm` component to add a new pet. This should add the new pet in your React app by updating the appropriate state and should additionally persist the added pet to the JSON Server database.
- Type in the `Search` component and see the list of pets whose name or animal_type match the text in the search bar. If there's no text in the search bar, all the pets should be rendered.

### Endpoints for Core Deliverables

#### GET /pets

Example Response:

```json
[
  {
    "id": 1,
    "name": "Fido",
    "fromPetShop": true,
    "image": "./images/dog.jpeg",
    "animal_type": "Dog"
  },
  {
    "id": 2,
    "name": "Kitty",
    "fromPetShop": true,
    "image": "./images/cat.png",
    "animal_type": "Cat"
  }
]
```

#### POST `/pets`

Required Headers:

```javascript
{
  "Content-Type": "application/json"
}
```

Request Object:

```json
{
  "name": "string",
  "fromPetShop": boolean,
  "image": "string",
  "animal_type": "string"
}
```

Example Response:

```json
{
  "id": 7,
  "name": "Goldie",
  "fromPetShop": true,
  "image": "./images/fish.jpeg",
  "animal_type": "Fish"
}
```

## Advanced Deliverables

If you have the extra time, these Advanced Deliverables are a great way to
stretch your skills.

You may have to add additional elements for these features. Feel free to style
them however you see fit!

As a user:

1. I can update the name of a pet and still see the updated name after
   refreshing the page.
2. I can delete a pet when clicking the "Adopt Pet" button and it is still gone when I refresh the page.

### Endpoints for Advanced Deliverables

#### PATCH /pets/:id

Required Headers:

```js
{
  "Content-Type": "application/json"
}
```

Request Object:

```json
{
  "name": "string"
}
```

Example Response:

```json
{
  "id": 1,
  "name": "Fido",
  "fromPetShop": true,
  "image": "./images/dog.jpeg",
  "animal_type": "Dog"
}
```

#### DELETE /pets/:id

Example Response:

```json
{}
```
