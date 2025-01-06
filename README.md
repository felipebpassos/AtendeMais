<p align="center" style="color: gray;">
    <i>⚠️ This project is currently under development.</i>
</p>

<h1 align="center" style="font-weight: bold;">Atende+</h1>

<p align="center">
 <a href="#about">About</a> • 
 <a href="#tech">Technologies</a> • 
 <a href="#architecture">Architecture</a> • 
 <a href="#screenshots">Screenshots</a> • 
 <a href="#colab">Collaborators</a>
</p>

![Banner](https://github.com/felipebpassos/HealupPublic/blob/main/img/healup-screenshots.png?raw=true)

<p align="center">
    Telemedicine marketplace for online appointments and scheduling.
</p>

<p align="center">
    <a href="https://youtu.be/OjWBcroxG0Y"><img src="https://img.shields.io/badge/YouTube-Demo-red?style=for-the-badge&logo=youtube"></a>
</p>

<br>

<h2 id="about">📝 About</h2>

**Atende+** provides an accessible telemedicine platform, built with **React Native** and **Node.js**, that allows patients to easily connect with healthcare professionals, schedule appointments, and have secure video consultations—all from the convenience of their mobile devices (Android and iOS). It offers a range of features, including:

- **Schedule and Appointment Management**: Patients and healthcare professionals can manage availability, book appointments, and receive reminders.
- **Advanced Search**: Advanced paginated search functionality with filters to help users find professionals by specialty, price, or location.
- **Video Calls**: Integrated video call functionality using WebRTC protocol for secure and seamless consultations.
- **File Uploads**: Upload and manage medical files and images directly within the app.
- **Notifications**: Automated email notifications and push notifications to keep users updated.
- **Payments**: Secure payment processing with credit card tokenization and PIX integration via ASAAS.
- **Real-time Notifications**: Configured WebSocket server for instant notifications.
- **Two-Factor Authentication (2FA)**: Ensuring platform security and user identity verification.

<br>

<h2 id="tech">💻 Technologies</h2>

<br>

- **Frontend**: React Native, Expo SDK 52, Styled Components
- **HTTP Requests**: Axios, Fetch API for parsing and handling API requests
- **State Management**: Redux, Context and Provider
- **Backend**: Node.js, Express.js, API REST
- **Database**: Sequelize, MySQL
- **Storage**: AWS S3 for file uploads
- **Authentication**: JWT, Two-Factor Authentication (2FA)
- **Payments**: ASAAS for credit card and PIX integration
- **Real-Time Communication**: WebRTC for video calls, WebSockets for live updates
- **Caching**: Redis for optimized data retrieval
- **Notifications**: Push Notifications with Firebase

<br>

<h2 id="architecture">🏗️ Architecture Overview</h2>

<p>
  Atende+ was built with a modular and scalable architecture, making it easy to maintain and extend. Below is an overview of the main layers of the project along with examples from the code.
</p>

<h3>1. Frontend (React Native)</h3>
<p>
  The frontend handles all user interface interactions and consumes the backend API to fetch data and execute functionalities.
</p>

<p><b>Folder structure:</b></p>
<pre>
<code>
src/
├── components/
│   ├── Header.js
│   ├── ButtonPrimary.js
│   ├── ProfileImage.js
│   ├── ProfessionalCard.js
├── screens/
│   ├── LoginScreen.js
│   ├── PatientDashboardScreen.js
│   ├── ProfessionalDashboardScreen.js
│   ├── AppointmentsScreen.js
│   ├── PaymentsScreen.js
├── redux/
│   ├── slices/
│   │   ├── userSlice.js
|   |   ├── searchSlice.js
|   |   ├── promotionsSlice.js
│   │   ├── horariosSlice.js
│   ├── store.js
├── context/
|   ├── AuthContext.js
│   ├── AlertContext.js
│   ├── FinalizedConsultationContext.js
├── hooks/
│   ├── useAuth.js
│   ├── useProfilePicture.js
│   ├── useWebSockets.js
├── utils/
│   ├── formatDate.js
│   ├── emailValidator.js
│   ├── agendamentosUtils.js
├── navigation/
│   ├── DashboardTabs.js
│   ├── StackNavigator.js
</code>
</pre>

<p><b>Redux Slice Example:</b></p>
<img
  src="https://github.com/felipebpassos/HealupPublic/blob/main/img/redux-slice-example.png?raw=true"
  alt="Redux Slice Example"
  width="100%"
/>
<p>
  <i>This code snippet demonstrates how global state is managed using Redux. Each slice represents a specific feature of the application.</i>
</p>

<p><b>Auth Context Example:</b></p>
<img
  src="https://github.com/felipebpassos/HealupPublic/blob/main/img/auth-context-example.png?raw=true"
  alt="Auth Context Example"
  width="100%"
/>
<p>
  <i>This example illustrates how authentication data is managed using React's Context API for sharing state globally.</i>
</p>

<p><b>Navigation Setup:</b></p>
<img
  src="https://github.com/felipebpassos/HealupPublic/blob/main/img/navigation-setup-example.png?raw=true"
  alt="Navigation Setup Example"
  width="100%"
/>
<p>
  <i>The navigation folder contains <code>DashboardTabs.js</code> for managing bottom tab navigation and <code>StackNavigator.js</code> for managing the app's stack navigator, ensuring a seamless user experience.</i>
</p>

<br>

<h3>2. Backend (Node.js + Express.js)</h3>
<p>
  The backend provides a RESTful API for managing data and integrates external services like ASAAS for payment processing and AWS S3 for file storage.
</p>

<p><b>Folder structure:</b></p>
<pre>
<code>
backend/
├── controllers/
│   ├── authController.js
│   ├── appointmentController.js
├── models/
│   ├── User.js
│   ├── Appointment.js
├── routes/
│   ├── authRoutes.js
│   ├── appointmentRoutes.js
├── app.js
</code>
</pre>

<p><b>Express Route Example:</b></p>
<img
  src="https://github.com/felipebpassos/HealupPublic/blob/main/img/express-route-example.png?raw=true"
  alt="Express Route Example"
  width="100%"
/>
<p>
  <i>This example shows a protected route using JWT authentication to list user appointments.</i>
</p>

<br>

<h3>3. Database (MySQL)</h3>
<p>
  The database is managed with Sequelize ORM, providing flexible data manipulation and model definitions.
</p>

<p><b>Sequelize Model Example:</b></p>
<img
  src="https://github.com/felipebpassos/HealupPublic/blob/main/img/sequelize-model-example.png?raw=true"
  alt="Sequelize Model Example"
  width="100%"
/>
<p>
  <i>This model defines the structure of the <code>appointments</code> table and its associations with other models.</i>
</p>

<br>

<h3>4. External Integrations</h3>
<p>
  The application integrates with various external services to enhance functionality:
</p>
<ul>
  <li><b>Payments (ASAAS):</b> For processing payments via PIX and credit cards.</li>
  <li><b>Video Calls (WebRTC):</b> For secure and seamless online consultations.</li>
  <li><b>Notifications (Firebase):</b> For push notifications to keep users updated.</li>
</ul>

<p><b>ASAAS Integration Example:</b></p>
<img
  src="https://github.com/felipebpassos/HealupPublic/blob/main/img/asaas-integration-example.png?raw=true"
  alt="ASAAS Integration Example"
  width="100%"
/>

<br>

<h2 id="screenshots">📱 Screenshots</h2>

<p>
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148011.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148038.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733411624.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148141.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148075.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148088.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148132.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733150182.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148159.png?raw=true" alt="Image Example" width="150px">
    <img src="https://github.com/felipebpassos/HealupPublic/blob/main/img/Screenshot_1733148166.png?raw=true" alt="Image Example" width="150px">
</p>

<br>

<h2 id="colab">🤝 Collaborators</h2>

<table>
  <tr>
    <td align="center">
      <a href="#">
        <img src="https://avatars.githubusercontent.com/u/93273305?v=4" width="100px;" alt="Felipe Passos Profile Picture"/><br>
        <sub>
          <b>Felipe Passos</b><br>Lead Developer
        </sub>
      </a>
    </td>
    <td align="center">
      <a href="#">
        <img src="https://avatars.githubusercontent.com/u/110487985?v=4" width="100px;" alt="Yuri Profile Picture"/><br>
        <sub>
          <b>Yuri</b><br>Front-End Developer
        </sub>
      </a>
    </td>
  </tr>
</table>
