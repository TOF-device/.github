# **TOF-KSA — Advanced People Counting & Analytics System (AlMajed4Oud)**

TOF-KSA is a full-stack, real-time people counting and footfall analytics platform powered by high-accuracy **Time-of-Flight (TOF)** sensors. It enables organizations to monitor entries, exits, and live occupancy, visualize footfall trends, generate reports, and manage connected TOF devices efficiently.

The system is composed of:

* **Next.js Client** — modern dashboards, reports, and device management UI
* **Spring Boot Server** — device communication, heartbeat processing, and data analytics backend

---

## 📖 **Project Overview**

TOF-KSA provides a complete solution for:

* Real-time people counting
* Crowd flow analytics
* Device health monitoring
* Organization-level data management
* Secure access control

Designed for malls, enterprises, retail spaces, universities, and public facilities looking to optimize visitor insights and operational decisions.

---

## 🚀 **Key Features**

### **📊 Real-Time Analytics Dashboard**

* Live footfall monitoring with instant updates
* Current occupancy, total entries, and exits
* Interactive charts (Recharts) for data visualization

### **📈 Comprehensive Reporting**

* Historical trend analysis (hourly, daily, monthly)
* Aggregated data for business insights (e.g., peak hours, conversion rates)
* Date range filtering and detailed breakdowns

### **📡 Device Management**

* Live Heartbeat monitoring for all TOF devices
* Remote device configuration (business hours, upload intervals, settings)
* Secure HTTP-based communication (`/HeartBeat`, `/DataUpload`)

### **🛡️ Security & Access Control**

* JWT authentication (Spring Security)
* Role-based access: **Admin**, **Developer**, **Organization**, **Viewer**
* Strict data visibility per organization

---

## 🛠️ **Technology Stack**

### **Frontend (Client) — Next.js**

* **Framework:** Next.js 15 (React 19 + App Router)
* **Styling:** Tailwind CSS, `tailwindcss-animate`
* **UI:** Radix UI, Shadcn UI
* **Icons:** Lucide React
* **Charts:** Recharts
* **Forms/Validation:** react-hook-form, zod
* **Date Utilities:** date-fns

### **Backend (Server) — Spring Boot**

* **Framework:** Spring Boot 3.4 (Java 21)
* **Database:** MySQL (JPA/Hibernate)
* **Auth:** JWT (jjwt)
* **Cloud Storage:** AWS S3
* **Utilities:** Lombok, FastJSON

---

## 🏗️ **System Architecture**

### **1. Data Collection**

TOF devices send:

* **Heartbeat** payloads → device status
* **DataUpload** payloads → entries/exits & time-stamped movement events

### **2. Processing Layer (Server)**

* Validates device payloads
* Updates population counters
* Stores historical data in MySQL
* Manages device active/inactive states

### **3. Visualization Layer (Client)**

* Fetches live and historical data via secure REST APIs
* Displays dashboards, reports, device details, and user management pages

---

## 📂 **Frontend Architecture & Folder Structure**

```
src/
  app/
    (dashboard)/
      devices-and-users/
        page.tsx
      live-data/
        page.tsx
      reports/
        page.tsx
      layout.tsx
    globals.css
    layout.tsx
    page.tsx

  components/
    auth/
      LoginView.tsx
      OwnerForm.tsx
      UserTypeRadioBtns.tsx
      ViewerForm.tsx
    dashboard/
      CustomSidebarTrigger.tsx
      DashboardSidebar.tsx
      LogoutBtn.tsx
      SideBarMenuLinks.tsx
    devices-and-users/
      CreateDeviceForm.tsx
      CreateOptionsRadio.tsx
      CreateUserForm.tsx
      DeviceDetails.tsx
      DevicesAndUserdView.tsx
      DeviceSpecs.tsx
      SelectPermissionType.tsx
    global/
      LiveDateAndTime.tsx
      Loader.tsx
      ModeToggleBtn.tsx
      MultiSelect.tsx
      SelectDevice.tsx
    layouts/
      NavBar.tsx
    live-data/
      CurrentPeopleInside.tsx
      DisplayLiveData.tsx
      Enquiries.tsx
      LiveDataError.tsx
      LiveDataSelectWraper.tsx
      LiveDataView.tsx
      LiveDataWraper.tsx
      TotalInside.tsx
    reports/
      Charts.tsx
      DatePicker.tsx
      DisplayDataAtPeriod.tsx
      DisplayTotalDataAtPeriod.tsx
      FromToDatePickers.tsx
      ReportsPageSelectWraper.tsx
      ReportsView.tsx
    ui/
      badge.tsx
      button.tsx
      calendar.tsx
      card.tsx
      chart.tsx
      command.tsx
      dialog.tsx
      dropdown-menu.tsx
      form.tsx
      input.tsx
      label.tsx
      multi-select.tsx
      password-input.tsx
      popover.tsx
      radio-group.tsx
      select.tsx
      separator.tsx
      sheet.tsx
      sidebar.tsx
      skeleton.tsx
      toast.tsx
      toaster.tsx
      tooltip.tsx

  constants/
    chartConfigs.ts
    testData.ts

  contexts/
    devices-and-users-context.tsx
    live-data-context.tsx
    reports-data-context.tsx
    theme-provider.tsx

  hooks/
    use-mobile.tsx
    use-toast.ts
    useCreateDeviceForm.ts
    useCreateUserForm.ts
    useOwnerForm.ts
    useReportsChartsBoxes.ts
    useReportsData.ts
    useViewerForm.ts

  lib/
    validations/
      CreateDeviceFormSchema.ts
      CreateUserFormSchema.ts
      OwnerFormSchema.ts
      ViewerFormSchema.ts
    utils.ts

  types/
    detectionEntry.ts
    formMethods.ts
    inputOnUserTypeProps.ts
    liveDataCtxValues.ts
    RangeResults.ts
    reduceTotalDataProps.ts
    reportsData.ts
    RequestName.ts

  utils/
    fetchDataForDate.ts
    fetchLiveData.ts
    fetchUser.ts
    fetchUserDevices.ts
    formatLiveDataDate.ts
    formatLiveDataTime.ts
    getDatesInRange.ts
    getToken.ts
    handleAllDaysArray.ts
    handleShowErrors.ts
    handleTotalResults.ts
    logout.ts
    onCreateDeviceSubmit.ts
    onCreateUserSubmit.ts
    onOwnerFormSubmit.ts
    onViewerFormSubmit.ts
    reduceTotal.ts

  middleware.ts

.gitignore  
.prettierrc  
components.json  
eslint.config.mjs  
next.config.ts  
package.json  
postcss.config.mjs  
README.md  
tailwind.config.ts  
tsconfig.json
```

---

## 📦 **Installation & Setup**

### **1. Clone the Repository**

```bash
git clone https://github.com/your-org/tof-ksa.git
cd tof-ksa
```

### **2. Install Client Dependencies**

```bash
cd client
npm install
npm run dev
```

### **3. Install Server Dependencies**

```bash
cd server
mvn clean install
mvn spring-boot:run
```

> Make sure MySQL is running and environment variables are configured.

---

## 🔐 **Environment Variables**

### **Client**

```
NEXT_PUBLIC_API_URL=
```

### **Server**

```
DB_URL=
DB_USERNAME=
DB_PASSWORD=
JWT_SECRET=
AWS_ACCESS_KEY=
AWS_SECRET_KEY=
AWS_S3_BUCKET=
```

---

## 📊 **Dashboard Previews** *(Optional — add screenshots)*

You can include images like:

```
![Dashboard](./public/dashboard-preview.png)
```

---

## 🤝 **Contributing**

Contributions, issues, and feature requests are welcome.
Follow conventional commits and PR templates if contributing.

---

## 📜 **License**

This project is licensed under the **MIT License**.

