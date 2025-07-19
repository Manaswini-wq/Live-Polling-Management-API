# Live Polling Management API

A simple Flask-based backend to manage live polling functionality with the following features:

## ✅ Features Implemented

### 🎯 Milestone 1: Prevent Multiple Votes Per User

* Each `user_identifier` can vote only once per poll.
* Additional votes are blocked with a response like `{ "status": "already_voted" }`.

### 📌 Milestone 2: List All Active Polls

* `GET /polls/active` returns all polls with `status = 'active'`.
* Helps in showing only open polls to users.

### 🔒 Milestone 3: Close a Poll

* `PUT /polls/<poll_str_id>/status` updates poll status.
* Closed polls reject new votes with `{ "error": "Poll is closed" }`.

---

## 🛠 Tech Stack

* **Python**
* **Flask**
* **SQLite** (can be replaced with any relational DB)
* **SQLAlchemy** ORM

---

## 📦 Setup Instructions

1. **Clone this repository**

   ```bash
   git clone https://github.com/yourusername/live-polling-api.git
   cd live-polling-api
   ```

2. **Install dependencies**

   ```bash
   pip install flask flask_sqlalchemy
   ```

3. **Run the app**

   ```bash
   python live_polling_api.py
   ```

4. **Test Endpoints** using tools like Postman or cURL:

   * `POST /polls/<poll_str_id>/vote`
   * `GET /polls/active`
   * `PUT /polls/<poll_str_id>/status`

---

## 🧪 Sample JSON Requests

### 🗳 Vote

```json
POST /polls/fav_color/vote
{
  "user_identifier": "user123",
  "option_id": 2
}
```

### 🛑 Close Poll

```json
PUT /polls/fav_color/status
{
  "status": "closed"
}
```

---

## 📄 License

This project is open-source and free to use under the MIT License.

---

## 🙋‍♀️ Author

**Manaswini Shroff**

LinkedIn: [manaswini-s](https://www.linkedin.com/in/manaswini-s-191927286/)
GitHub: [Manaswini-wq](https://github.com/Manaswini-wq)
