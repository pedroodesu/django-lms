# Django LMS

A lightweight Learning Management System built with Django. Instructors can create courses, lessons, and exams; learners can browse courses, enroll, and take exams to test their knowledge.

## Features

- User registration and authentication (learners)
- Course catalog with lessons
- Course enrollment
- Multiple-choice exams per course, with automatic grading
- Exam results page showing pass/fail status and per-question feedback
- Full Django admin panel for managing courses, lessons, questions, and choices

## Tech Stack

- **Backend**: Python, Django
- **Frontend**: Django Templates, Bootstrap
- **Database**: SQLite (default; supports PostgreSQL/MySQL)

## Data Model

- `Course` — has many `Lesson`s and `Question`s, and many `Instructor`s
- `Lesson` — belongs to a `Course`
- `Question` — belongs to a `Course`, has many `Choice`s
- `Choice` — belongs to a `Question`, may be marked as correct
- `Enrollment` — links a `User` to a `Course`
- `Submission` — an exam attempt, linking an `Enrollment` to the selected `Choice`s

## Getting Started

### Prerequisites
- Python 3.11+
- pip

### Setup

```bash
# Clone the repository
git clone https://github.com/pedroodesu/django-lms.git
cd django-lms

# Create and activate a virtual environment
python -m venv myenv
myenv\Scripts\activate      # Windows
# source myenv/bin/activate  # macOS/Linux

# Install dependencies
pip install -r requirements.txt

# Apply migrations
python manage.py makemigrations onlinecourse
python manage.py migrate

# Create an admin user
python manage.py createsuperuser

# Run the development server
python manage.py runserver
```

Visit `http://127.0.0.1:8000/onlinecourse/` for the app, or `http://127.0.0.1:8000/admin` for the admin panel.

## License

This project is licensed under the Apache 2.0 License.