# Aleksejunas Fileserver Project

Welcome to 👋 **PodFiles** 👋, a full-stack web application project that includes a file-server backend and a React front-end, designed to run using Podman containers. The application enables file uploads and serves files through a simple and user-friendly interface.

## Project Structure

```
project-root/
├── backend/ # Node.js file server
├── frontend/ # React application for the front-end
└── ansible/ # Ansible playbooks for automation
```

## Features

- **File Server**: A Node.js server with Express and Multer for handling file uploads.
- **React Front-End**: A responsive interface for uploading and accessing files.
- **Containerization**: Both backend and frontend are Dockerized and run in a Podman pod.
- **Automation**: Ansible playbooks for automated deployment and configuration.

## Getting Started

### Prerequisites

Ensure you have the following installed:

- Node.js (v16 or higher)
- Podman
- Ansible (for automation)
- Git

### Installation

1. **Clone the Repository**:

   ```
   git clone https://github.com/yourusername/aleksejunas-fileserver.git
   cd aleksejunas-fileserver

   ```

2. **Backend Setup**:

   ```
   cd backend
   pnpm install

   ```

3. Frontend Setup

   ```bash
   cd frontend
   pnpm install
   ```

### Running the Application

#### Using Podman

1. **Build Docker Images**:

```bash
cd backend
podman build -t my-backend-image .

cd ../frontend
podman build -t my-frontend-image .
```

2. **Create and Run a Pod**:

```



# Aleksejunas Fileserver Project

This is a full-stack web application project that includes a file server backend and a React front-end, designed to run using Podman containers. The application enables file uploads and serves files through a simple and user-friendly interface.

## Project Structure

```

project-root/
├── backend/ # Node.js file server
├── frontend/ # React application for the front-end
└── ansible/ # Ansible playbooks for automation

````

## Features

- **File Server**: A Node.js server with Express and Multer for handling file uploads.
- **React Front-End**: A responsive interface for uploading and accessing files.
- **Containerization**: Both backend and frontend are Dockerized and run in a Podman pod.
- **Automation**: Ansible playbooks for automated deployment and configuration.

## Getting Started

### Prerequisites

Ensure you have the following installed:
- Node.js (v16 or higher)
- Podman
- Ansible (for automation)
- Git

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/aleksejunas-fileserver.git
   cd aleksejunas-fileserver
````

2. **Backend Setup**:

   ```bash
   cd backend
   npm install
   ```

3. **Frontend Setup**:

   ```bash
   cd ../frontend
   npm install
   ```

### Running the Application

#### Using Podman

1. **Build Docker Images**:

   ```bash
   cd backend
   podman build -t my-backend-image .

   cd ../frontend
   podman build -t my-frontend-image .
   ```

2. **Create and Run a Pod**:

   ```bash
   podman pod create --name mypod -p 8080:3000 -p 8081:3001
   podman run -d --pod mypod --name backend-container my-backend-image
   podman run -d --pod mypod --name frontend-container my-frontend-image
   ```

### Usage

- Access the front-end at `http://localhost:8080`
- The backend API runs on `http://localhost:8081`

### Deployment with Ansible

1. **Prepare Inventory**:
   Create an inventory file:

   ```ini
   [fileserver]
   your-server-ip ansible_user=your-ssh-username
   ```

2. **Run the Playbook**:

   ```bash
   ansible-playbook -i inventory.ini ansible/deploy_fileserver.yml
   ```

## Future Enhancements

- Add user authentication.
- Integrate cloud storage options.
- Implement security measures such as SSL/TLS.

## Contributing

Contributions are welcome! Feel free to open issues or create pull requests.

## License

This project is licensed under the MIT License. See `LICENSE` for details.

## Contact

Developed by [Your Name](https://yourdomain.com)

For inquiries, please email: [youremail@example.com](mailto:youremail@example.com)
