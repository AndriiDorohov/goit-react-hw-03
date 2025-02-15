# Homework

## Created Repository: `goit-react-hw-03`

- Repository: **goit-react-hw-03**
- When submitting the homework, provide two links: one to the source files and one to the deployed page on **Vercel**.
- The project was created using **Vite**.
- The **Formik** library is used for creating forms.
- During the task execution, there are no errors or warnings in the console.
- For each component in the `src/components` folder, there is a separate folder containing the JSX file for the React component and the corresponding styles file. The folder name, component file (with the `.jsx` extension), and styles file (with `.module.css` before the extension) have the same name and match the names specified in the tasks (if provided).
- **Default export** is used for components.
- The JS code is clean and readable, using **Prettier**.
- The styling is done using **CSS modules**.``

---

## Task 3 - Phonebook

## Contacts Book

Create an application for storing contacts in a phonebook.  
The application should consist of:

- A **form** for adding contacts.
- A **contact list** displaying saved contacts.
- A **search field** for filtering the contact list.

Watch the demo video to see the application's functionality.

## Components

In this task, the interface is already divided into components.  
Your task is to **define the state and props** and implement them in the code.  
The parts of the interface that belong to a component are highlighted with a corresponding **colored border**.

![enter image description here](https://github.com/AndriiDorohov/goit-react-hw-03/blob/main/src/assets/img_01.png?raw=true)

### Component Structure

The application should be divided into the following components:

1. **Root Component (`App`)** – The main component that manages the state.
2. **Contact Form** – A form for adding new contacts.
3. **Contact List** – A list displaying saved contacts.
4. **Contact Item** – A single contact entry in the list.
5. **Search Filter** – A field for filtering contacts by name.

All components are rendered inside the `App` component.  
Its structure will look like this, along with props and additional logic.

```jsx
<div>
  <h1>Phonebook</h1>
  <ContactForm />
  <SearchBox />
  <ContactList />
</div>`
```

### Step 1 - Contact List

The `App` component should store the **contacts** in its state as an array.

During development, it's convenient to hardcode some initial data in the state.  
This avoids manually entering contacts for testing new functionality.

Use the following **array of contacts** as the initial state:

```jsx
const initialContacts = [
  { id: 'id-1', name: 'Rosie Simpson', number: '459-12-56' },
  { id: 'id-2', name: 'Hermione Kline', number: '443-89-12' },
  { id: 'id-3', name: 'Eden Clements', number: '645-17-79' },
  { id: 'id-4', name: 'Annie Copeland', number: '227-91-26' },
];
```

Create the ContactList and Contact components and use them to display the contact list. Pass the necessary values via props.

After this step, the application's interface will look as follows – a page header and a contact list.

![enter image description here](https://github.com/AndriiDorohov/goit-react-hw-03/blob/main/src/assets/img_02.png?raw=true)

### Step 2 - Search by Name

Add a `SearchBox` input field that can be used to filter the contact list by name.

The search field should be an uncontrolled input, with its value stored in the state (controlled component). The filtering logic should be case-insensitive.

The filter state should be stored in the `App` component and passed as a prop to the `SearchBox` component. The filtering of the contacts array will be done in the `App` component, and the filtered contacts array will be passed as a prop to the `ContactList` component.

After this step, when text is entered in the search field, the contact list should update to show only matching contacts.

### Step 3 - Adding Contacts

At this stage, implement adding a contact to the contact list via the `ContactForm` form. Each contact should be an object with the properties `name`, `number`, and `id`, just like in the test data currently in your state.

To generate unique identifiers, use any appropriate package, such as `nanoid`. In the future, this will be handled by a database, but for now, we add the object identifier manually, for example, during form submission.

The form must be created using the `Formik` library. Add validation for the form fields using the `Yup` library, and display error messages:

- Fields should be required.
- Minimum character length - 3.
- Maximum character length - 50.

After completing this step, the application should look something like this.

### Step 4 - Deleting Contacts

Expand the functionality of the application by allowing the user to delete previously saved contacts by clicking the "Delete" button on the contact card.

### Step 5 - Storing Contacts

The application should store the array of contacts in local storage between page reloads. Use effects for this.

When adding or deleting a contact, the contacts are saved to local storage.
When the application loads, contacts (if any) are read from local storage and written to the state.
