# JoblyTrack

A Django-based job application tracking system to help you manage your job search process effectively.

## Features

- **Job Management**: Track job applications with status updates (Wishlist, Applied, Interview, Offer, Rejected)
- **Interview Scheduling**: Schedule and manage interviews with automated reminders
- **Dashboard**: Get an overview of your job search progress with statistics and recent activity
- **Kanban Board**: Visual representation of your job application pipeline
- **User Authentication**: Secure user registration and login system
- **Responsive Design**: Works on desktop and mobile devices

## Tech Stack

- **Backend**: Django 5.0+, Django REST Framework
- **Frontend**: HTML, CSS (Tailwind CSS), JavaScript
- **Database**: SQLite (development), PostgreSQL (production)
- **Authentication**: Django's built-in authentication system
- **Styling**: Tailwind CSS

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd joblytrack
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env file with your settings
   ```

5. **Run migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create a superuser**
   ```bash
   python manage.py createsuperuser
   ```

7. **Run the development server**
   ```bash
   python manage.py runserver
   ```

Visit `http://127.0.0.1:8000` to access the application.

## Project Structure

```
joblytrack/
├── accounts/          # User authentication and management
├── jobs/             # Job application tracking
├── interviews/       # Interview scheduling and management
├── dashboard/        # Main dashboard views
├── templates/        # Global templates
├── static/          # Static files (CSS, JS, images)
├── joblytrack/      # Project settings
└── manage.py        # Django management script
```

## Usage

1. **Register/Login**: Create an account or log in to access the system
2. **Add Jobs**: Start by adding job applications you're interested in
3. **Track Progress**: Update job status as you progress through the application process
4. **Schedule Interviews**: Add interview details when you get scheduled
5. **Monitor Dashboard**: Use the dashboard to get an overview of your progress

## API Endpoints

The application includes REST API endpoints for programmatic access:

- `/api/jobs/` - Job management endpoints
- `/api/interviews/` - Interview management endpoints
- `/api/accounts/` - User management endpoints

## Management Commands

### Send Interview Reminders
```bash
python manage.py run_reminders
```
This command sends email reminders for interviews scheduled for the next day.

## Deployment

### Using Heroku

1. **Install Heroku CLI** and login
2. **Create a Heroku app**
   ```bash
   heroku create your-app-name
   ```
3. **Set environment variables**
   ```bash
   heroku config:set SECRET_KEY=your-secret-key
   heroku config:set DEBUG=False
   heroku config:set ALLOWED_HOSTS=your-app-name.herokuapp.com
   ```
4. **Deploy**
   ```bash
   git push heroku main
   ```

### Manual Deployment

1. Set up a PostgreSQL database
2. Configure environment variables for production
3. Run migrations
4. Collect static files: `python manage.py collectstatic`
5. Set up a web server (nginx + gunicorn recommended)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For support or questions, please open an issue on the repository or contact the development team.
