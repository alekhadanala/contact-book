# contact-book

contacts = []


def add_contact():
    name = input("Enter the name: ")
    phone = input("Enter the phone number: ")
    email = input("Enter the email: ")

    contact = {"name": name, "phone": phone, "email": email}
    contacts.append(contact)
    print("Contact added successfully!\n")


def view_contacts():
    if len(contacts) == 0:
        print("No contacts saved.\n")
        return

    print("\nSaved contacts:")
    for contact in contacts:
        print("Name:", contact["name"])
        print("Phone:", contact["phone"])
        print("Email:", contact["email"])
       # print("-" * 20)


def search_contact():
    search = input("Enter the name or phone to search: ")
    for contact in contacts:
        if contact["name"] == search or contact["phone"] == search:
            print("\nContact found:")
            print("Name:", contact["name"])
            print("Phone:", contact["phone"])
            print("Email:", contact["email"])
            return
    print("Contact not found.\n")


def delete_contact():
    name = input("Enter the name of contact to delete: ")
    for contact in contacts:
        if contact["name"] == name:
            contacts.remove(contact)
            print("Contact deleted successfully!\n")
            return
    print("Contact not found.\n")


# Main menu loop
while True:
    print("\n--- Contact Book ---")
    print("1. Add contact")
    print("2. View contacts")
    print("3. Search contact")
    print("4. Delete contact")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_contact()
    elif choice == "2":
        view_contacts()
    elif choice == "3":
        search_contact()
    elif choice == "4":
        delete_contact()
    elif choice == "5":
        print("Thanks for using the contact book!")
        break
    else:
        print("Invalid choice, try again.\n")
