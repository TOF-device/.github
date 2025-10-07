# TOF Device Management System — Frontend (AlMajed4Oud)

A modern, scalable dashboard application built for **AlMajed4Oud**, a leading Saudi Arabian company.  
This project is designed to manage, monitor, and control **TOF devices** used across multiple global branches, providing real-time analytics, user role management, and operational insights — all from a unified web interface.

---

## Overview

The TOF Device Management System enables administrators and managers to oversee thousands of devices deployed worldwide.  
It provides a seamless experience for real-time device tracking, user role management, and detailed reporting, ensuring efficient monitoring and decision-making across distributed networks.

---

## Key Features

- **Real-Time Device Monitoring**: Track and visualize live device activity and status across branches worldwide.
- **Branch & Role Management**: Create, update, and assign roles for staff, managers, and administrators within the system.
- **Comprehensive Reports**: Generate time-based reports and export them in Excel or PDF formats for operational insights.
- **User & Access Control**: Manage user accounts and permissions with secure authentication and role-based access.
- **Interactive Dashboard**: Visualize metrics through dynamic charts and tables with responsive, user-friendly UI.
- **Data Synchronization**: Real-time API integration ensures accurate and consistent device data updates across the system.

---

## Tech Stack

- **Next.js (App Router)** — Core framework for rendering and routing
- **TypeScript** — Strong typing for scalable and maintainable code
- **React Hook Form + Zod** — Form management and schema-based validation
- **Tailwind CSS** — Utility-first responsive design system
- **Chart.js** — Data visualization for real-time analytics
- **Axios** — API data fetching and integration
- **Lucide React** — Icon system for modern UI components
- **SweetAlert2** — Elegant modals and alerts for user notifications

---

## Architecture & Folder Structure

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

The architecture follows a **modular component-based structure** to promote scalability, reusability, and clean separation of concerns.

---

## Core Functionalities

- **Dashboard Overview** — Displays device counts, online/offline status, and activity summaries.
- **Device Management** — Allows managers to add, edit, or remove devices and assign them to specific branches.
- **Branch Management** — Supports global multi-branch structures for international operations.
- **Reporting System** — Enables export of analytics data as Excel or PDF for internal audits.
- **Role-Based Access Control (RBAC)** — Ensures data visibility and permissions are restricted by user role.

---

## Environment Variables

To configure your environment, create a `.env` file in the root directory with the following:

NEXT_PUBLIC_API_BASE_URL=<Your Backend API URL>

Add additional variables as required for production deployments.

---

## Getting Started

**Prerequisites**

- Node.js (LTS recommended)
- npm or yarn package manager

**Setup Instructions**

```bash
# clone the repository
git clone <repo-url>
cd tof-device-management-frontend

# install dependencies
npm install
# or
yarn

# configure environment
cp .env.example .env
# update NEXT_PUBLIC_API_BASE_URL with backend endpoint

# run in development mode
npm run dev

# build for production
npm run build
npm run start



Deployment

This app can be deployed to Vercel, Netlify, or any platform supporting Next.js.
Ensure NEXT_PUBLIC_API_BASE_URL points to the production backend server before deployment.

Contribution

Contributions are welcome! Please follow the steps below:

Fork the repository.

Create a new branch: git checkout -b feat/your-feature.

Commit and push your changes.

Open a pull request with a clear description of your modifications.

Please follow the existing code style (TypeScript + Tailwind + modular structure).

Security

Sensitive data such as tokens and API keys must not be committed.

Follow secure coding and data handling practices.

Use HTTPS for all API communications.

Maintainer

For inquiries, issues, or contributions, please open an issue on the repository or contact the maintainer directly.

```
