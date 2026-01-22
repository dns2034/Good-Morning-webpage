# How Did You Start Your Day?

A lightweight Django-based social journaling application that allows users to register, log in, and share their morning thoughts or daily starts through text-based posts.



## 🚀 Features

* **User Authentication:** Full registration, login, and logout functionality.
* **Secure Password Management:** Built-in "Change Password" feature for logged-in users.
* **Post Creation:** Users can create posts with a title and description using a clean, card-based UI.
* **Interactive Feed:** A real-time home feed displaying posts from all users in reverse chronological order.
* **Role-Based Permissions:**
    * **Users:** Can create posts and delete their own posts.
    * **Moderators:** Have permission to delete any post to maintain community standards.
    * **Staff:** Can "Ban" users by programmatically removing them from permission groups (`default` or `mod`).
* **Responsive UI:** Styled with **Bootstrap 5**, featuring a customized dark-brown horizontal navigation bar and a warm parchment-style background (`#E9E3D3`).

## 🛠️ Tech Stack

* **Backend:** Django (Python)
* **Frontend:** HTML5, CSS3, Bootstrap 5
* **Icons:** Bootstrap Icons (`bi-cup-hot`, `bi-key`, etc.)
* **Forms:** Django Crispy Forms with Bootstrap 5 styling.

## 📁 Project Structure (Logic Overview)

### Views & Controllers
* `home`: Handles the display of all posts. Includes logic to handle `POST` requests for deleting posts and banning users based on permission checks.
* `created_post`: Uses the `@permission_required` decorator to ensure only authorized users can contribute.
* `sign_up`: Manages new user registration and automatically logs the user in upon successful creation.

### Templates
* `base.html`: The master layout containing the horizontal navbar, global CSS overrides, and the Google Fonts/Bootstrap imports.
* `home.html`: Employs Django template logic to conditionally show "Delete" or "Ban" buttons only to users with the correct privileges.

## ⚙️ Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd <project-folder>
    ```

2.  **Install dependencies:**
    ```bash
    pip install django django-crispy-forms crispy-bootstrap5
    ```

3.  **Run Migrations:**
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

4.  **Group Setup (Important):**
    To use the moderation features, create the following groups in the Django Admin panel (`/admin`):
    * `default`: Basic posting permissions.
    * `mod`: Moderation and deletion permissions.

5.  **Start the server:**
    ```bash
    python manage.py runserver
    ```

## 📝 Usage

1.  Navigate to `/sign-up` to create a new account.
2.  Once logged in, you will be redirected to the **Your Feed**.
3.  Click **"Add Post"** to share your morning routine.
4.  Use the **Navbar** (top-right) to change your password or logout securely.

---
*Developed as a Django User Management & Authentication Project.*