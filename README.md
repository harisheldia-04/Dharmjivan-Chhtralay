<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dharmjivan Chhatralay</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
      background: #eef2f5;
      color: #333;
    }

    .login {
      width: 90%;
      max-width: 400px;
      margin: 60px auto;
      padding: 25px;
      background: white;
      border-radius: 16px;
      text-align: center;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }

    .login h1 {
      color: #1a73e8;
      margin-bottom: 5px;
      font-size: 24px;
    }

    input, textarea, select {
      width: 100%;
      padding: 11px;
      margin: 8px 0;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-family: inherit;
      font-size: 14px;
    }

    button {
      width: 100%;
      padding: 12px;
      margin-top: 10px;
      border: 0;
      border-radius: 8px;
      background: #1a73e8;
      color: white;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
    }

    button:disabled {
      cursor: not-allowed;
      background: #9e9e9e !important;
    }

    .header {
      background: #1a73e8;
      color: white;
      padding: 20px 15px;
      text-align: center;
      border-bottom-left-radius: 16px;
      border-bottom-right-radius: 16px;
    }

    .container {
      padding: 15px;
      max-width: 600px;
      margin: auto;
    }

    .grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-top: 15px;
    }

    .card {
      padding: 18px 8px;
      text-align: center;
      border-radius: 14px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.08);
      transition: transform 0.1s ease, box-shadow 0.1s ease;
      color: white;
    }

    .card:active {
      transform: scale(0.97);
    }

    .icon {
      font-size: 34px;
      display: block;
      margin-bottom: 6px;
    }

    .card-student-details {
      background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
    }

    .card-attendance {
      background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
    }

    .card-complaint {
      background: linear-gradient(135deg, #eb3349 0%, #f45c43 100%);
    }

    .card-notice {
      background: linear-gradient(135deg, #f7971e 0%, #ffd200 100%);
      color: #222 !important;
    }

    .card-notice small {
      color: #333 !important;
    }

    .card-night-check {
      background: linear-gradient(135deg, #4776e6 0%, #8e54e9 100%);
    }

    .card-contacts {
      background: linear-gradient(135deg, #00b4db 0%, #0083b0 100%);
    }

    .card-rector-default {
      background: white;
      color: #333;
    }

    .logout {
      background: #d93025;
      margin-top: 20px;
    }

    .complaint-card {
      background: #fff;
      border-left: 5px solid #d93025;
      padding: 12px;
      margin-bottom: 12px;
      border-radius: 6px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.06);
      text-align: left;
    }

    .smartwork-card {
      background: #fff;
      border-left: 5px solid #0f9d58;
      padding: 12px;
      margin-bottom: 12px;
      border-radius: 6px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.06);
      text-align: left;
    }

    .notice-card {
      background: #fff;
      border-left: 5px solid #1a73e8;
      padding: 14px;
      margin-bottom: 12px;
      border-radius: 6px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.06);
      text-align: left;
    }

    .profile-photo {
      width: 95px;
      height: 95px;
      border-radius: 50%;
      object-fit: cover;
      border: 3px solid #1a73e8;
      background: #f1f3f4;
    }

    .small-profile-photo {
      width: 50px;
      height: 50px;
      border-radius: 50%;
      object-fit: cover;
      border: 2px solid #1a73e8;
      background: #f1f3f4;
      flex-shrink: 0;
    }

    .table-profile-photo {
      width: 45px;
      height: 45px;
      border-radius: 50%;
      object-fit: cover;
      border: 2px solid #1a73e8;
      background: #f1f3f4;
    }

    .admin-req-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: #fff3e0;
      color: #e65100;
      border: 1px solid #ffb74d;
      padding: 6px 14px;
      border-radius: 20px;
      font-size: 12px;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 2px 4px rgba(0,0,0,0.05);
    }

    .slot-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 8px 12px;
      background: #f8f9fa;
      border-radius: 6px;
      margin-bottom: 6px;
      font-size: 13px;
    }

    .tab-btn-group {
      display: flex;
      gap: 8px;
      margin-bottom: 15px;
    }

    .tab-btn {
      flex: 1;
      padding: 10px;
      border-radius: 8px;
      border: 2px solid transparent;
      font-weight: bold;
      cursor: pointer;
      font-size: 14px;
      text-align: center;
      background: #f1f3f4;
      color: #555;
    }

    .tab-active-smart {
      background: #e6f4ea !important;
      color: #137333 !important;
      border-color: #0f9d58 !important;
    }

    .tab-active-complaint {
      background: #fce8e6 !important;
      color: #d93025 !important;
      border-color: #d93025 !important;
    }

    .filter-btn-bar {
      display: flex;
      gap: 8px;
      margin: 10px 0;
    }

    .status-filter-btn {
      flex: 1;
      padding: 8px;
      font-size: 13px;
      font-weight: bold;
      border-radius: 6px;
      border: 1px solid #ccc;
      background: white;
      color: #333;
      cursor: pointer;
      margin: 0;
    }

    .status-filter-btn.active-all {
      background: #1a73e8 !important;
      color: white !important;
      border-color: #1a73e8 !important;
    }

    .status-filter-btn.active-present {
      background: #0f9d58 !important;
      color: white !important;
      border-color: #0f9d58 !important;
    }

    .status-filter-btn.active-absent {
      background: #d93025 !important;
      color: white !important;
      border-color: #d93025 !important;
    }

    .alert-banner {
      background: #e8f0fe;
      border: 1px solid #1a73e8;
      border-radius: 8px;
      padding: 10px 12px;
      margin-bottom: 12px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 13px;
    }
  </style>
</head>

<body>

  <!-- 1. LOGIN PAGE -->
  <div id="loginPage" class="login">
    <div style="font-size: 60px;">🏠</div>
    <h1>Dharmjivan Chhatralay</h1>
    <p style="color: gray; margin-bottom: 20px;">Student & Rector Portal</p>
    <input id="studentId" type="text" placeholder="HR Number / Phone Number">
    <input id="password" type="password" placeholder="Password">
    <button type="button" onclick="login()">LOGIN</button>
  </div>

  <!-- 2. RECTOR / ADMIN DASHBOARD -->
  <div id="rectorDashboard" style="display: none; padding: 15px; max-width: 900px; margin: auto; background: white; min-height: 100vh;">
    
    <!-- Header -->
    <div style="background: #1a73e8; color: white; padding: 18px 20px; border-radius: 12px; margin-bottom: 20px;">
      <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 10px;">
        <div>
          <h2 style="margin: 0; font-size: 24px; font-weight: bold;" id="rectorWelcomeTitle">Rector Name</h2>
          <small id="rectorScopeBadge" style="background: #fff; color: #1a73e8; padding: 3px 8px; border-radius: 4px; font-weight: bold; margin-top: 6px; display: inline-block;">All Standards</small>
        </div>
        <div>
          <span style="font-size: 15px; color: #ffeb3b; font-weight: bold; background: rgba(0,0,0,0.25); padding: 7px 14px; border-radius: 8px; display: inline-block;">
            આપને હેતથી જય સ્વામિનારાયણ 🙏
          </span>
        </div>
      </div>
    </div>

    <!-- Quick Cards View (Rector) -->
    <div id="rectorCardsView">
      <!-- Approval Notice for Rector -->
      <div id="rectorPermissionNotice"></div>

      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; flex-wrap:wrap; gap:8px;">
        <h3 style="color: #333; margin: 0;">Quick Access</h3>
        <div style="display:flex; gap:8px;">
          <button type="button" id="btnRequestOtherWing" onclick="openRoomPermissionDialog()" style="width:auto; padding:6px 12px; font-size:12px; background:#673ab7; margin:0;">
            🤝 રિક્વેસ્ટ: અન્ય રૂમ/વિંગ હાજરી
          </button>
          <div id="adminUnlockRequestsBadge" class="admin-req-badge" style="display: none;" onclick="openAdminUnlockRequests()">
            <span>🔑 Requests Panel</span>
            <span id="unlockBadgeCount" style="background:#e65100; color:white; border-radius:10px; padding:2px 7px; font-size:11px;">0</span>
          </div>
        </div>
      </div>

      <div class="grid">
        <div class="card card-rector-default" onclick="openRectorStudentsView()">
          <span class="icon">👥</span>
          <b>Student List</b>
          <small style="display:block; color:gray; font-size:11px; margin-top:4px;">Students Directory</small>
        </div>
        <div class="card card-rector-default" onclick="openRectorAttendance()">
          <span class="icon">📊</span>
          <b>Attendance</b>
          <small style="display:block; color:gray; font-size:11px; margin-top:4px;">Mark Attendance</small>
        </div>
        <div class="card card-rector-default" onclick="openRectorNoticeView()">
          <span class="icon">📢</span>
          <b>Notice Board</b>
          <small style="display:block; color:gray; font-size:11px; margin-top:4px;">Publish Notice</small>
        </div>
        <div class="card card-rector-default" onclick="openRectorComplaintView()">
          <span class="icon">⚖️</span>
          <b>Smart Work / Complaint</b>
          <small style="display:block; color:gray; font-size:11px; margin-top:4px;">Positive & Negative</small>
        </div>
        <div class="card card-rector-default" onclick="openRectorNightCheckView()">
          <span class="icon">🌙</span>
          <b>Night Check</b>
          <small style="display:block; color:gray; font-size:11px; margin-top:4px;">Room Checking</small>
        </div>
        <div class="card card-rector-default" onclick="openRectorProfileView()">
          <span class="icon">👤</span>
          <b>My Profile</b>
          <small style="display:block; color:gray; font-size:11px; margin-top:4px;">Profile Details</small>
        </div>
      </div>

      <button type="button" class="logout" onclick="logout()" style="width: 100%; padding: 13px; font-size: 17px; margin-top: 25px; border-radius: 10px;">
        LOGOUT
      </button>
    </div>

    <!-- Student Table -->
    <div id="rectorTableView" style="display: none; margin-top: 15px;">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
        <h3 style="margin: 0; color: #1a73e8;">Student List</h3>
        <button type="button" onclick="backToRectorCards()" style="width: auto; padding: 6px 14px; background: #5f6368; color: white; border: none; border-radius: 6px; cursor: pointer; margin: 0; font-size: 14px;">← Back</button>
      </div>

      <div style="margin: 15px 0; display: flex; flex-wrap: wrap; gap: 10px;">
        <input type="text" id="searchBox" onkeyup="filterRectorStudents()" placeholder="Search Name, HR No, Father Phone..." style="flex: 2; min-width: 180px;">
        <select id="stdFilterDropdown" onchange="filterRectorStudents()" style="flex: 1; min-width: 120px;"></select>
        <select id="mediumFilterDropdown" onchange="filterRectorStudents()" style="flex: 1; min-width: 120px;"></select>
        <select id="studentListRoomDropdown" onchange="filterRectorStudents()" style="flex: 1; min-width: 120px;"></select>
      </div>

      <div style="overflow-x: auto;">
        <table border="1" style="width: 100%; border-collapse: collapse; text-align: left; background: white; font-size: 13px;">
          <thead style="background: #f1f3f4;">
            <tr>
              <th style="padding: 8px;">Photo</th>
              <th style="padding: 8px;">HR No</th>
              <th style="padding: 8px;">Name</th>
              <th style="padding: 8px;">Father / Phone</th>
              <th style="padding: 8px;">Standard</th>
              <th style="padding: 8px;">Room</th>
              <th style="padding: 8px;">Bed</th>
              <th style="padding: 8px; text-align: center;">Attendance</th>
            </tr>
          </thead>
          <tbody id="rectorStudentTbody"></tbody>
        </table>
      </div>
    </div>

    <!-- Attendance View -->
    <div id="rectorAttendanceView" style="display: none; margin-top: 15px;">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
        <h3 style="margin: 0; color: #1a73e8;">Daily Attendance</h3>
        <button type="button" onclick="backFromAttendance()" style="width: auto; padding: 6px 14px; background: #5f6368; color: white; border: none; border-radius: 6px; cursor: pointer; margin: 0; font-size: 14px;">← Back</button>
      </div>

      <div style="margin-bottom: 15px; display: flex; gap: 10px; align-items: center; flex-wrap: wrap;">
        <label><b>Select Date:</b></label>
        <input type="date" id="attendanceDate" style="width: auto; margin: 0; padding: 8px;" onchange="loadAttendanceForDate()">
      </div>

      <div style="background:#fff8e1; border:1px solid #f4b400; padding:12px; border-radius:8px; margin-bottom:15px;">
        <label style="display:flex; align-items:center; gap:8px; font-weight:bold; cursor:pointer;">
          <input type="checkbox" id="holidayAttendanceCheck" onchange="toggleTodayHoliday()" style="width:auto; margin:0;">
          📅 Holiday Attendance Mode
        </label>
        <small style="display:block; color:#666; margin-top:5px;">
          Slots: 7:45-8:00 AM, 10:00-10:30 AM, 12:30-1:30 PM, 3:00-3:45 PM, 5:00-5:30 PM, 8:30-9:00 PM
        </small>
      </div>

      <div style="margin: 15px 0; display: flex; flex-wrap: wrap; gap: 10px;">
        <input type="text" id="attSearchBox" onkeyup="loadAttendanceForDate()" placeholder="Search..." style="flex: 2; min-width: 180px;">
        <select id="attStdFilterDropdown" onchange="loadAttendanceForDate()" style="flex: 1; min-width: 120px;"></select>
        <select id="attMediumFilterDropdown" onchange="loadAttendanceForDate()" style="flex: 1; min-width: 120px;">
          <option value="ALL">All Medium</option>
          <option value="Gujarati">Gujarati Medium</option>
          <option value="English">English Medium</option>
        </select>
        <select id="attRoomFilterDropdown" onchange="loadAttendanceForDate()" style="flex: 1; min-width: 120px;">
          <option value="ALL">All Rooms</option>
        </select>
      </div>

      <!-- Present / Absent Filter Bar -->
      <div class="filter-btn-bar">
        <button type="button" id="attFilterAll" class="status-filter-btn active-all" onclick="filterAttendanceStatus('ALL')">👥 All Students</button>
        <button type="button" id="attFilterPresent" class="status-filter-btn" onclick="filterAttendanceStatus('PRESENT')">✅ Present Only</button>
        <button type="button" id="attFilterAbsent" class="status-filter-btn" onclick="filterAttendanceStatus('ABSENT')">❌ Absent Only</button>
      </div>

      <div style="overflow-x: auto;">
        <table border="1" style="width: 100%; border-collapse: collapse; text-align: left; background: white; font-size: 14px;">
          <thead style="background: #f1f3f4;">
            <tr>
              <th style="padding: 8px;">HR No</th>
              <th style="padding: 8px;">Name</th>
              <th style="padding: 8px;">Standard</th>
              <th style="padding: 8px;">Room</th>
              <th style="padding: 8px; text-align: center;">Status & Reason</th>
            </tr>
          </thead>
          <tbody id="attendanceTbody"></tbody>
        </table>
      </div>

      <div id="attendanceActionArea" style="margin-top: 15px;">
        <button type="button" id="saveAttendanceBtn" onclick="saveAttendance()" style="background: #0f9d58;">SAVE ATTENDANCE</button>
        <div id="attWhatsAppShareArea" style="margin-top:10px; display:none;">
          <button type="button" onclick="sendAdminAttendanceSummary('ATTENDANCE')" style="background:#25d366; color:white;">
            📲 WhatsApp એડમિનને ગેરહાજર વિદ્યાર્થીઓનું લિસ્ટ મોકલો
          </button>
        </div>
        <button type="button" id="requestUnlockAttBtn" onclick="requestAdminUnlock('ATTENDANCE')" style="display: none; background: #e37400; margin-top: 10px;">
          🔑 REQUEST ADMIN UNLOCK (Attendance Time Closed)
        </button>
      </div>
    </div>

    <!-- Admin Requests Panel (Time Unlock + Room Permission Requests) -->
    <div id="adminUnlockView" style="display: none; margin-top: 15px;">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
        <h3 style="margin: 0; color: #b06000;">🔑 All Requests & Permissions</h3>
        <button type="button" onclick="backFromUnlockView()" style="width: auto; padding: 6px 14px; background: #5f6368; color: white; border: none; border-radius: 6px; cursor: pointer; margin: 0; font-size: 14px;">← Back</button>
      </div>
      <div id="unlockRequestsContainer"></div>
    </div>

    <!-- Notice Board -->
    <div id="rectorNoticeView" style="display: none; margin-top: 15px;">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
        <h3 style="margin: 0; color: #1a73e8;">Notice Board Management</h3>
        <button type="button" onclick="backFromNotice()" style="width: auto; padding: 6px 14px; background: #5f6368; color: white; border: none; border-radius: 6px; cursor: pointer; margin: 0; font-size: 14px;">← Back</button>
      </div>

      <div style="background: #f9f9f9; padding: 15px; border-radius: 8px; border: 1px solid #ddd; margin-bottom: 20px;">
        <h4 style="margin: 0 0 10px 0; color: #333;">Publish New Notice</h4>
        
        <label><b>1. Target Audience:</b></label>
        <select id="noticeTargetSelect"></select>

        <label style="margin-top: 8px; display:block;"><b>2. Attach Photo (Optional - Marjiyat):</b></label>
        <input type="file" id="noticeImageInput" accept="image/*" style="margin-bottom: 4px;">

        <label style="margin-top: 8px; display:block;"><b>3. Notice Title:</b></label>
        <input type="text" id="noticeTitleInput" placeholder="Title...">

        <label style="margin-top: 8px; display:block;"><b>4. Notice Details:</b></label>
        <textarea id="noticeDetailInput" rows="3" placeholder="Enter details..."></textarea>

        <button type="button" onclick="publishNotice()" style="background: #1a73e8; margin-top: 10px;">PUBLISH NOTICE</button>
      </div>

      <h4 style="color: #333; margin-bottom: 10px;">Previous Notices:</h4>
      <div id="rectorNoticeListContainer"></div>
    </div>

    <!-- Smart Work & Complaints View -->
    <div id="rectorComplaintView" style="display: none; margin-top: 15px;">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
        <h3 style="margin: 0; color: #1a73e8;">Smart Work & Complaints</h3>
        <button type="button" onclick="backFromComplaint()" style="width: auto; padding: 6px 14px; background: #5f6368; color: white; border: none; border-radius: 6px; cursor: pointer; margin: 0; font-size: 14px;">← Back</button>
      </div>

      <div class="tab-btn-group">
        <div id="tabSmartWorkBtn" class="tab-btn tab-active-smart" onclick="switchRecordTab('SMARTWORK')">
          🌟 Smart Work (Positive)
        </div>
        <div id="tabComplaintBtn" class="tab-btn" onclick="switchRecordTab('COMPLAINT')">
          📝 Complaint (Negative)
        </div>
      </div>

      <div style="background: #f9f9f9; padding: 15px; border-radius: 8px; border: 1px solid #ddd; margin-bottom: 20px;">
        <h4 id="recordFormTitle" style="margin: 0 0 10px 0; color: #0f9d58;">Add Smart Work Record (Sari Pravrutti)</h4>
        <input type="text" id="complaintSearchInput" placeholder="Filter student list..." onkeyup="filterComplaintStudents()">
        <select id="complaintStudentSelect" onchange="onComplaintStudentChanged()"></select>

        <label style="margin-top: 10px; display:block;"><b>Category:</b></label>
        <select id="complaintTypeSelect"></select>

        <label style="margin-top: 10px; display:block;"><b>Photo (Optional - જો ફોટો મૂકવો હોય તો):</b></label>
        <input type="file" id="recordImageInput" accept="image/*">

        <label style="margin-top: 10px; display:block;"><b>Details / Description:</b></label>
        <textarea id="complaintDetailInput" rows="3" placeholder="Enter details here..."></textarea>

        <button type="button" id="submitRecordBtn" onclick="submitStudentRecord()" style="background: #0f9d58; margin-top: 10px;">SUBMIT SMART WORK</button>
      </div>

      <h4 id="complaintListHeader" style="color: #333; margin-bottom: 10px;">Records List:</h4>
      <div id="rectorComplaintListContainer"></div>
    </div>

    <!-- Night Check View -->
    <div id="rectorNightCheckView" style="display: none; margin-top: 15px;">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
        <h3 style="margin: 0; color: #1a73e8;">🌙 Night Round (10:15 - 11:00 PM)</h3>
        <button type="button" onclick="backFromNightCheck()" style="width: auto; padding: 6px 14px; background: #5f6368; color: white; border: none; border-radius: 6px; cursor: pointer; margin: 0; font-size: 14px;">← Back</button>
      </div>

      <div style="background: #f9f9f9; padding: 15px; border-radius: 8px; border: 1px solid #ddd; margin-bottom: 15px;">
        <div style="display:flex; gap:10px; flex-wrap:wrap; align-items:center;">
          <div style="flex:1; min-width:140px;">
            <label><b>Check Date:</b></label>
            <input type="date" id="nightCheckDate" style="margin:4px 0 0 0;" onchange="loadNightCheckForRoom()">
          </div>
          <div style="flex:1; min-width:140px;">
            <label><b>Select Room:</b></label>
            <select id="nightCheckRoomSelect" style="margin:4px 0 0 0;" onchange="loadNightCheckForRoom()"></select>
          </div>
        </div>

        <div style="margin-top:10px;">
          <label><b>Search Student:</b></label>
          <input type="text" id="nightCheckSearchInput" placeholder="Search by name, HR No or father phone..." style="margin:4px 0 0 0;" onkeyup="loadNightCheckForRoom()">
        </div>
      </div>

      <!-- Present / Absent Filter Bar for Night Check -->
      <div class="filter-btn-bar">
        <button type="button" id="ncFilterAll" class="status-filter-btn active-all" onclick="filterNightCheckStatus('ALL')">👥 All Students</button>
        <button type="button" id="ncFilterPresent" class="status-filter-btn" onclick="filterNightCheckStatus('PRESENT')">✅ Present Only</button>
        <button type="button" id="ncFilterAbsent" class="status-filter-btn" onclick="filterNightCheckStatus('ABSENT')">❌ Absent Only</button>
      </div>

      <div id="nightCheckStudentsContainer"></div>

      <div style="margin-top: 15px; background: white; padding: 12px; border: 1px solid #ccc; border-radius: 8px;">
        <label><b>Room Remarks:</b></label>
        <textarea id="nightCheckRoomRemark" rows="2" placeholder="Write room remarks..." style="margin-top: 5px;"></textarea>
        <button type="button" id="saveNightCheckBtn" onclick="saveNightCheckReport()" style="background: #0f9d58; margin-top: 10px;">SAVE ROOM CHECKING</button>
        <div id="ncWhatsAppShareArea" style="margin-top:10px; display:none;">
          <button type="button" onclick="sendAdminAttendanceSummary('NIGHT_CHECK')" style="background:#25d366; color:white;">
            📲 WhatsApp એડમિનને નાઇટ ચેક ગેરહાજર લિસ્ટ મોકલો
          </button>
        </div>
        <button type="button" id="requestUnlockNightBtn" onclick="requestAdminUnlock('NIGHT_CHECK')" style="display: none; background: #e37400; margin-top: 10px;">
          🔑 REQUEST ADMIN UNLOCK (Night Check Locked)
        </button>
      </div>
    </div>

    <!-- Rector Profile -->
    <div id="rectorProfileView" style="display: none; margin-top: 15px; text-align: center;">
      <div style="display: flex; justify-content: flex-end; margin-bottom: 15px;">
        <button type="button" onclick="backFromRectorProfile()" style="width: auto; padding: 6px 14px; background: #5f6368; color: white; border: none; border-radius: 6px; cursor: pointer; margin: 0; font-size: 14px;">← Back</button>
      </div>
      <div style="background: #f9f9f9; padding: 25px; border-radius: 12px; border: 1px solid #ddd; max-width: 450px; margin: auto;">
        <div style="position:relative; width:100px; margin:0 auto 10px auto;">
          <img id="profRectorPhoto" class="profile-photo" src="" alt="Rector Photo">
          <label for="rectorPhotoInput" style="display:inline-block; margin-top:8px; background:#1a73e8; color:white; padding:4px 10px; border-radius:6px; font-size:12px; cursor:pointer;">
            📷 Change
          </label>
          <input type="file" id="rectorPhotoInput" accept="image/*" onchange="updateRectorPhoto(this)" style="display:none;">
        </div>

        <h2 id="profRectorName" style="margin: 15px 0 5px 0; color: #1a73e8; font-size: 24px;">-</h2>
        <p style="color: gray; margin: 0 0 15px 0; font-weight: bold;" id="profRectorRoleDisplay">Hostel Rector</p>
        <hr style="border: 0; border-top: 1px solid #eee; margin: 15px 0;">
        <p style="text-align: left; margin: 6px 0;"><b>Phone:</b> <span id="profRectorPhone">-</span></p>
        <p style="text-align: left; margin: 6px 0;"><b>Standard:</b> <span id="profRectorStd">-</span></p>
        <p style="text-align: left; margin: 6px 0;"><b>Medium:</b> <span id="profRectorMed">-</span></p>
      </div>
    </div>
  </div>

  <!-- 3. STUDENT HOME PAGE -->
  <div id="home" style="display: none;">
    <div class="header">
      <h1 style="margin:0 0 5px 0;">Dharmjivan Chhatralay</h1>
      <p style="margin:0; opacity:0.9;">Student Management App</p>
    </div>
    <div class="container">
      <h2>Welcome 👋</h2>
      <div style="display:flex; align-items:center; gap:12px; margin-bottom:15px; background:white; padding:12px; border-radius:14px; box-shadow:0 3px 8px rgba(0,0,0,0.06);">
        <img id="studentHomePhoto" class="small-profile-photo" src="" alt="Student Photo">
        <div>
          <p id="student" style="font-weight: bold; font-size: 18px; color: #1a73e8; margin:0;"></p>
          <small style="color:gray;">Student Dashboard</small>
        </div>
      </div>

      <h2>Quick Access</h2>
      <div class="grid">
        <div class="card card-student-details" onclick="studentDetails()">
          <span class="icon">🦁</span>
          <b>Student Details</b>
          <small style="display:block; color:rgba(255,255,255,0.85); font-size:11px; margin-top:4px;">Full Profile</small>
        </div>

        <div class="card card-attendance" onclick="viewStudentAttendance()">
          <span class="icon">📊</span>
          <b>Attendance</b>
          <small id="studentCardAttendanceBadge" style="display:block; color:#ffffff; font-size:11px; font-weight:bold; margin-top:4px; text-shadow:0 1px 2px rgba(0,0,0,0.2);">100% Attendance</small>
        </div>

        <div class="card card-complaint" onclick="viewStudentComplaints()">
          <span class="icon">⚖️</span>
          <b>Smart Work / Complaint</b>
          <small style="display:block; color:rgba(255,255,255,0.9); font-size:11px; margin-top:4px;">Positive & Negative</small>
        </div>

        <div class="card card-notice" onclick="viewStudentNotices()">
          <span class="icon">📢</span>
          <b>Notice</b>
          <small style="display:block; font-size:11px; margin-top:4px;">New Notices</small>
        </div>

        <div class="card card-night-check" onclick="viewStudentNightCheck()">
          <span class="icon">🌙</span>
          <b>Night Check</b>
          <small style="display:block; color:rgba(255,255,255,0.85); font-size:11px; margin-top:4px;">Night Status</small>
        </div>

        <div class="card card-contacts" onclick="viewHostelContacts()">
          <span class="icon">📞</span>
          <b>Hostel Contacts</b>
          <small style="display:block; color:rgba(255,255,255,0.85); font-size:11px; margin-top:4px;">Office Help</small>
        </div>
      </div>

      <button type="button" class="logout" onclick="logout()">LOGOUT</button>
    </div>
  </div>

  <div id="studentSubPage" style="display: none; padding: 15px; max-width: 500px; margin: auto;"></div>

  <script src="students.js"></script>

  <script>
    // એડમિનનો વોટ્સએપ નંબર (જરૂર મુજબ બદલી શકો છો)
    const ADMIN_WHATSAPP_NUMBER = "";

    let currentStudent = null;
    let currentRector = null;
    let currentAttendanceData = {};
    let currentAttendanceReasons = {};
    let currentNightCheckData = {};
    let currentNightCheckReasons = {};
    let activeRecordTab = "SMARTWORK";
    let activeStudentRecordTab = "SMARTWORK";
    let currentAttViewStatusFilter = "ALL";
    let currentNcViewStatusFilter = "ALL";

    window.addEventListener("DOMContentLoaded", () => {
      const savedUserType = localStorage.getItem("hostel_user_type");
      const savedUserId = localStorage.getItem("hostel_user_id");

      if (savedUserType === "rector" && savedUserId) {
        if (savedUserId.toLowerCase() === "nirmalswami") {
          applyRectorLogin(getAdminFallbackObject());
          return;
        }
        const rector = (window.rectors || []).find(r => String(r.id) === savedUserId || String(r.phone) === savedUserId);
        if (rector) {
          applyRectorLogin(rector);
          return;
        }
      } else if (savedUserType === "student" && savedUserId) {
        const student = (window.students || []).find(s => String(s.id) === savedUserId);
        if (student) {
          applyStudentLogin(student);
          return;
        }
      }
      document.getElementById("loginPage").style.display = "block";
    });

    function getAdminFallbackObject() {
      return {
        id: "Nirmalswami",
        name: "Nirmalswami",
        password: "Admin 86251",
        role: "ADMIN",
        std: "ALL",
        medium: "ALL",
        wing: "ALL"
      };
    }

    /* PROFILE PHOTO SYSTEM */
    function getPhotoStore() {
      return JSON.parse(localStorage.getItem("hostel_profile_photos") || "{}");
    }

    function savePhotoStore(store) {
      localStorage.setItem("hostel_profile_photos", JSON.stringify(store));
    }

    function getStudentPhoto(student) {
      if (!student) return "";
      const store = getPhotoStore();
      return store["student_" + String(student.id)] || student.photo || defaultStudentPhoto();
    }

    function getRectorPhoto(rector) {
      if (!rector) return "";
      const key = rector.id || rector.phone || rector.name || "unknown";
      const store = getPhotoStore();
      return store["rector_" + String(key)] || rector.photo || defaultRectorPhoto();
    }

    function defaultStudentPhoto() {
      return "data:image/svg+xml;charset=UTF-8," + encodeURIComponent(`
        <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100">
          <rect width="100" height="100" fill="#e8f0fe"/>
          <text x="50" y="62" text-anchor="middle" font-size="48">👨‍🎓</text>
        </svg>
      `);
    }

    function defaultRectorPhoto() {
      return "data:image/svg+xml;charset=UTF-8," + encodeURIComponent(`
        <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100">
          <rect width="100" height="100" fill="#e8f0fe"/>
          <text x="50" y="62" text-anchor="middle" font-size="48">👤</text>
        </svg>
      `);
    }

    function updateRectorPhoto(input) {
      if (!currentRector || !input.files || !input.files[0]) return;
      const file = input.files[0];
      const reader = new FileReader();
      reader.onload = function(e) {
        const store = getPhotoStore();
        const key = currentRector.id || currentRector.phone || currentRector.name;
        store["rector_" + String(key)] = e.target.result;
        savePhotoStore(store);
        document.getElementById("profRectorPhoto").src = e.target.result;
        alert("Rector profile photo updated successfully!");
      };
      reader.readAsDataURL(file);
    }

    function updateStudentPhoto(input) {
      if (!currentStudent || !input.files || !input.files[0]) return;
      const file = input.files[0];
      const reader = new FileReader();
      reader.onload = function(e) {
        const store = getPhotoStore();
        store["student_" + String(currentStudent.id)] = e.target.result;
        savePhotoStore(store);
        const homePhoto = document.getElementById("studentHomePhoto");
        if (homePhoto) homePhoto.src = e.target.result;
        alert("Profile photo updated successfully!");
        studentDetails();
      };
      reader.readAsDataURL(file);
    }

    /* LOGIN */
    function login() {
      try {
        const idInput = (document.getElementById("studentId").value || "").trim();
        const passInput = (document.getElementById("password").value || "").trim();
        if (!idInput || !passInput) {
          alert("Please enter HR Number/ID and Password!");
          return;
        }

        const isNirmalId = (idInput.toLowerCase() === "nirmalswami" || idInput.toLowerCase() === "nirmal swami");
        const isNirmalPass = (passInput === "Admin 86251" || passInput.replace(/\s+/g,'') === "Admin86251");

        if (isNirmalId && isNirmalPass) {
          const adminObj = (window.rectors || []).find(r => r.name === "Nirmalswami" || r.id === "Nirmalswami") || getAdminFallbackObject();
          adminObj.role = "ADMIN";
          adminObj.std = "ALL";
          adminObj.medium = "ALL";
          adminObj.wing = "ALL";
          
          localStorage.setItem("hostel_user_type", "rector");
          localStorage.setItem("hostel_user_id", "Nirmalswami");
          applyRectorLogin(adminObj);
          return;
        }

        const rector = (window.rectors || []).find(r => 
          (String(r.id).trim() === idInput || String(r.phone).trim() === idInput) && String(r.password).trim() === passInput
        );

        if (rector) {
          localStorage.setItem("hostel_user_type", "rector");
          localStorage.setItem("hostel_user_id", String(rector.id || rector.phone));
          applyRectorLogin(rector);
          return;
        }

        const student = (window.students || []).find(s => 
          String(s.id).trim() === idInput && String(s.password).trim() === passInput
        );

        if (student) {
          localStorage.setItem("hostel_user_type", "student");
          localStorage.setItem("hostel_user_id", String(student.id));
          applyStudentLogin(student);
          return;
        }

        alert("Invalid HR Number or Password!");
      } catch (err) {
        alert("Login Error: " + err.message);
      }
    }

    function applyRectorLogin(rector) {
      currentRector = rector;
      document.getElementById("loginPage").style.display = "none";
      document.getElementById("rectorDashboard").style.display = "block";
      document.getElementById("rectorCardsView").style.display = "block";
      document.getElementById("rectorTableView").style.display = "none";

      document.getElementById("rectorWelcomeTitle").innerText = rector.name || "Rector";
      
      const badgeEl = document.getElementById("rectorScopeBadge");
      const adminBadgeBtn = document.getElementById("adminUnlockRequestsBadge");
      const btnRequestOtherWing = document.getElementById("btnRequestOtherWing");

      if (rector.role === "ADMIN" || rector.name === "Nirmalswami") {
        badgeEl.innerText = "👑 Chief Admin";
        badgeEl.style.background = "#ffd700";
        badgeEl.style.color = "#000";
        if (adminBadgeBtn) {
          adminBadgeBtn.style.display = "inline-flex";
          updateUnlockBadgeCount();
        }
        if (btnRequestOtherWing) btnRequestOtherWing.style.display = "none";
      } else {
        const wingText = rector.wing ? ("Wing " + rector.wing + " | ") : "";
        badgeEl.innerText = wingText + "STD " + (Array.isArray(rector.std) ? rector.std.join("&") : rector.std);
        badgeEl.style.background = "#e6f4ea";
        badgeEl.style.color = "#137333";
        if (adminBadgeBtn) adminBadgeBtn.style.display = "none";
        if (btnRequestOtherWing) btnRequestOtherWing.style.display = "inline-block";
        checkRectorApprovedPermissionsBanner();
      }

      setupRectorStrictFilters();
    }

    function applyStudentLogin(student) {
      currentStudent = student;
      document.getElementById("loginPage").style.display = "none";
      document.getElementById("home").style.display = "block";
      document.getElementById("student").innerText = (student.firstName || '') + " " + (student.surname || '');
      document.getElementById("studentHomePhoto").src = getStudentPhoto(student);
      updateStudentCardAttendanceBadge();
    }

    function logout() {
      if (!confirm("Are you sure you want to log out?")) return;
      localStorage.removeItem("hostel_user_type");
      localStorage.removeItem("hostel_user_id");
      currentStudent = null;
      currentRector = null;
      currentAttendanceData = {};
      currentAttendanceReasons = {};
      currentNightCheckData = {};
      currentNightCheckReasons = {};

      document.getElementById("home").style.display = "none";
      document.getElementById("rectorDashboard").style.display = "none";
      document.getElementById("studentSubPage").style.display = "none";
      document.getElementById("loginPage").style.display = "block";
      document.getElementById("studentId").value = "";
      document.getElementById("password").value = "";
    }

    /* RECTOR PROXY ROOM PERMISSION LOGIC */
    function getRectorAllowedRooms(rector) {
      if (!rector) return [];
      const permissions = JSON.parse(localStorage.getItem("hostel_room_permissions") || "{}");
      const rId = String(rector.id || rector.phone || rector.name);
      const userPerm = permissions[rId] || [];
      const activeRooms = [];
      const now = Date.now();
      userPerm.forEach(p => {
        if (p.expireTime > now && Array.isArray(p.rooms)) {
          activeRooms.push(...p.rooms.map(String));
        }
      });
      return [...new Set(activeRooms)];
    }

    function checkRectorApprovedPermissionsBanner() {
      if (!currentRector) return;
      const banner = document.getElementById("rectorPermissionNotice");
      const allowedRooms = getRectorAllowedRooms(currentRector);
      if (allowedRooms.length > 0) {
        banner.innerHTML = `
          <div class="alert-banner">
            <div>
              <b>✅ એડમિન પરમિશન મળેલ છે:</b> રૂમ નં. <b>${allowedRooms.join(", ")}</b> ની હાજરી પૂરવાની છૂટ છે.
            </div>
            <button type="button" onclick="notifyRectorAcknowledge()" style="width:auto; padding:3px 8px; font-size:11px; background:#1a73e8; margin:0;">OK</button>
          </div>
        `;
      } else {
        banner.innerHTML = "";
      }
    }

    function notifyRectorAcknowledge() {
      document.getElementById("rectorPermissionNotice").innerHTML = "";
    }

    function isStudentInRectorWing(s, r) {
      if (!r || !s) return false;
      if (r.role === "ADMIN" || r.role === "ALL_RECTOR" || r.name === "Nirmalswami" || r.std === "ALL") return true;

      // Check if student's room is temporarily approved by admin for this rector
      const proxyRooms = getRectorAllowedRooms(r);
      if (s.room && proxyRooms.includes(String(s.room))) {
        return true;
      }

      const stdNum = String(s.stdNumber || s.class || "").replace(/\D/g, "");
      const medium = s.medium || (String(s.class || "").toLowerCase().includes("th") ? "English" : "Gujarati");

      if (r.std && r.std !== "ALL") {
        const stdMatch = Array.isArray(r.std) ? r.std.map(String).includes(stdNum) : (String(r.std) === stdNum);
        if (!stdMatch) return false;
      }

      if (r.medium && r.medium !== "ALL") {
        if (r.medium.toLowerCase() !== medium.toLowerCase()) return false;
      }

      if (r.wing && r.wing !== "ALL" && s.wing) {
        if (String(s.wing).toLowerCase() !== String(r.wing).toLowerCase()) return false;
      }

      return true;
    }

    /* RECTOR REQUESTS FOR OTHER ROOMS/WING */
    function openRoomPermissionDialog() {
      if (!currentRector) return;
      const roomsInput = prompt("તમારે કયા રૂમ નંબરની હાજરી પૂરવી છે? (અલ્પવિરામથી લખો, દા.ત. 101, 102, 105):");
      if (!roomsInput || !roomsInput.trim()) return;

      const reason = prompt("બીજા રૂમ/વિંગની હાજરી પૂરવાનું કારણ લખો (જેમ કે: બીજા રેક્ટર ગેરહાજર છે):");
      if (!reason || !reason.trim()) return;

      const roomArray = roomsInput.split(",").map(r => r.trim()).filter(Boolean);
      const rectorId = String(currentRector.id || currentRector.phone || currentRector.name);
      const rectorPhone = currentRector.phone || "";

      const requests = JSON.parse(localStorage.getItem("hostel_unlock_requests") || "[]");
      const newReq = {
        id: Date.now(),
        type: "ROOM_PERMISSION",
        rectorId: rectorId,
        rectorName: currentRector.name,
        rectorPhone: rectorPhone,
        rooms: roomArray,
        reason: reason,
        requestTime: new Date().toLocaleTimeString("en-US", { hour: '2-digit', minute: '2-digit' }),
        status: "PENDING"
      };

      requests.unshift(newReq);
      localStorage.setItem("hostel_unlock_requests", JSON.stringify(requests));

      // એડમિનને વોટ્સએપ મેસેજ મોકલવાનો વિકલ્પ
      const msg = `*નવી પરમિશન રિક્વેસ્ટ (Dharmjivan Chhatralay)*%0A%0A*રેક્ટર:* ${currentRector.name}%0A*રૂમ નંબર્સ:* ${roomArray.join(", ")}%0A*કારણ:* ${reason}%0A*સમય:* ${newReq.requestTime}%0A%0Aકૃપા કરીને પોર્ટલ પર જઈને Approve કરો.`;
      const waUrl = `https://wa.me/${ADMIN_WHATSAPP_NUMBER}?text=${msg}`;

      if (confirm("રિક્વેસ્ટ નોંધાઈ ગઈ છે! શું એડમિનને સીધો WhatsApp મેસેજ મોકલવો છે?")) {
        window.open(waUrl, "_blank");
      } else {
        alert("રિક્વેસ્ટ એડમિન પેનલમાં મોકલી દેવાઈ છે.");
      }
    }

    /* UNLOCK REQUESTS & ADMIN PANEL */
    function requestAdminUnlock(type) {
      const reason = prompt("Enter reason for unlock (વિલંબનું કારણ લખો):");
      if (!reason) return;

      const rectorId = String(currentRector.id || currentRector.phone || currentRector.name);
      const requests = JSON.parse(localStorage.getItem("hostel_unlock_requests") || "[]");
      const newReq = {
        id: Date.now(),
        rectorId: rectorId,
        rectorName: currentRector.name,
        rectorPhone: currentRector.phone || "",
        type: type,
        reason: reason,
        requestTime: new Date().toLocaleTimeString("en-US", { hour: '2-digit', minute: '2-digit' }),
        status: "PENDING"
      };

      requests.unshift(newReq);
      localStorage.setItem("hostel_unlock_requests", JSON.stringify(requests));

      const msg = `*સમય અનલોક રિક્વેસ્ટ*%0A%0A*રેક્ટર:* ${currentRector.name}%0A*પ્રકાર:* ${type}%0A*કારણ:* ${reason}%0A*સમય:* ${newReq.requestTime}`;
      if (confirm("રિક્વેસ્ટ નોંધાઈ છે. એડમિનને WhatsApp કરવો છે?")) {
        window.open(`https://wa.me/${ADMIN_WHATSAPP_NUMBER}?text=${msg}`, "_blank");
      }
    }

    function openAdminUnlockRequests() {
      document.getElementById("rectorCardsView").style.display = "none";
      document.getElementById("adminUnlockView").style.display = "block";
      loadAdminUnlockRequests();
    }

    function backFromUnlockView() {
      document.getElementById("adminUnlockView").style.display = "none";
      document.getElementById("rectorCardsView").style.display = "block";
    }

    function loadAdminUnlockRequests() {
      const container = document.getElementById("unlockRequestsContainer");
      const requests = JSON.parse(localStorage.getItem("hostel_unlock_requests") || "[]");

      if (requests.length === 0) {
        container.innerHTML = `<p style="color:gray; padding:15px; text-align:center;">No pending requests at present.</p>`;
        return;
      }

      let html = "";
      requests.forEach(r => {
        const isPending = (r.status === "PENDING");
        const isRoomReq = (r.type === "ROOM_PERMISSION");

        html += `
          <div style="background:#f9f9f9; border:1px solid #ddd; padding:12px; margin-bottom:12px; border-radius:8px;">
            <div style="display:flex; justify-content:space-between; flex-wrap:wrap;">
              <b>${r.rectorName} - <span style="color:#1a73e8;">${isRoomReq ? '🤝 અન્ય રૂમ પરમિશન' : r.type}</span></b>
              <small style="color:gray;">${r.requestTime}</small>
            </div>
            ${isRoomReq ? `<p style="margin:5px 0; color:#1a73e8; font-weight:bold;">માંગેલ રૂમ: [ ${r.rooms.join(", ")} ]</p>` : ''}
            <p style="margin:5px 0; color:#555; font-size:13px;"><b>કારણ:</b> ${r.reason}</p>
            <div style="margin-top:8px;">
              ${isPending ? (
                isRoomReq ? `
                  <button type="button" onclick="grantRoomPermission(${r.id}, 120)" style="width:auto; padding:5px 12px; font-size:12px; background:#0f9d58; margin-right:5px;">✅ Approve (2 કલાક)</button>
                  <button type="button" onclick="grantRoomPermission(${r.id}, 360)" style="width:auto; padding:5px 12px; font-size:12px; background:#1a73e8; margin-right:5px;">✅ Approve (આજનો આખો દિવસ)</button>
                  <button type="button" onclick="rejectUnlock(${r.id})" style="width:auto; padding:5px 12px; font-size:12px; background:#d93025;">❌ Reject</button>
                ` : `
                  <button type="button" onclick="grantUnlock(${r.id}, 10)" style="width:auto; padding:5px 10px; font-size:12px; background:#0f9d58; margin-right:5px;">Allow 10 Min</button>
                  <button type="button" onclick="grantUnlock(${r.id}, 20)" style="width:auto; padding:5px 10px; font-size:12px; background:#1a73e8; margin-right:5px;">Allow 20 Min</button>
                  <button type="button" onclick="rejectUnlock(${r.id})" style="width:auto; padding:5px 10px; font-size:12px; background:#d93025;">Reject</button>
                `
              ) : `
                <span style="font-size:12px; font-weight:bold; color:${r.status==='APPROVED'?'#0f9d58':'#d93025'};">Status: ${r.status}</span>
                ${(r.status === 'APPROVED' && r.rectorPhone) ? `
                  <button type="button" onclick="sendApprovalWhatsAppToRector('${r.rectorPhone}', '${r.rectorName}', '${isRoomReq ? r.rooms.join(', ') : r.type}')" style="width:auto; padding:4px 10px; font-size:11px; background:#25d366; color:white; margin-left:10px;">
                    📲 રેક્ટરને WhatsApp મોકલો
                  </button>
                ` : ''}
              `}
            </div>
          </div>
        `;
      });
      container.innerHTML = html;
      updateUnlockBadgeCount();
    }

    function grantRoomPermission(requestId, minutes) {
      let requests = JSON.parse(localStorage.getItem("hostel_unlock_requests") || "[]");
      const req = requests.find(r => r.id === requestId);
      if (!req) return;

      const expireTimestamp = Date.now() + (minutes * 60 * 1000);
      const permissions = JSON.parse(localStorage.getItem("hostel_room_permissions") || "{}");
      if (!permissions[req.rectorId]) permissions[req.rectorId] = [];

      permissions[req.rectorId].push({
        rooms: req.rooms,
        expireTime: expireTimestamp,
        approvedAt: new Date().toLocaleTimeString("en-US")
      });
      localStorage.setItem("hostel_room_permissions", JSON.stringify(permissions));

      req.status = "APPROVED";
      req.duration = minutes;
      localStorage.setItem("hostel_unlock_requests", JSON.stringify(requests));

      alert(`રૂમ નં. ${req.rooms.join(", ")} ની પરમિશન ${req.rectorName} ને આપવામાં આવી છે!`);
      loadAdminUnlockRequests();

      // રેક્ટરને વોટ્સએપ પર જાણ કરવી
      if (req.rectorPhone) {
        sendApprovalWhatsAppToRector(req.rectorPhone, req.rectorName, `રૂમ નં. ${req.rooms.join(", ")} ની હાજરી`);
      }
    }

    function sendApprovalWhatsAppToRector(phone, name, details) {
      let p = phone.replace(/\D/g, "");
      if (p.length === 10) p = "91" + p;
      const msg = `જય સ્વામિનારાયણ ${name} જી,%0A%0Aએડમિન દ્વારા તમારી રિક્વેસ્ટ *[ ${details} ]* સ્વીકારી લેવામાં આવી છે. હવે તમે એપ્લિકેશનમાં હાજરી પૂરી શકો છો.`;
      window.open(`https://wa.me/${p}?text=${msg}`, "_blank");
    }

    function grantUnlock(requestId, minutes) {
      let requests = JSON.parse(localStorage.getItem("hostel_unlock_requests") || "[]");
      const req = requests.find(r => r.id === requestId);
      if (!req) return;

      const expireTimestamp = Date.now() + (minutes * 60 * 1000);
      const permissions = JSON.parse(localStorage.getItem("hostel_unlock_permissions") || "{}");
      if (!permissions[req.rectorId]) permissions[req.rectorId] = {};
      
      permissions[req.rectorId][req.type] = expireTimestamp;
      localStorage.setItem("hostel_unlock_permissions", JSON.stringify(permissions));

      req.status = "APPROVED";
      req.duration = minutes;
      localStorage.setItem("hostel_unlock_requests", JSON.stringify(requests));

      alert("Unlocked " + req.type + " for " + req.rectorName + " for " + minutes + " minutes!");
      loadAdminUnlockRequests();

      if (req.rectorPhone) {
        sendApprovalWhatsAppToRector(req.rectorPhone, req.rectorName, `${req.type} (${minutes} મિનિટ માટે)`);
      }
    }

    function rejectUnlock(requestId) {
      let requests = JSON.parse(localStorage.getItem("hostel_unlock_requests") || "[]");
      const req = requests.find(r => r.id === requestId);
      if (!req) return;
      req.status = "REJECTED";
      localStorage.setItem("hostel_unlock_requests", JSON.stringify(requests));
      loadAdminUnlockRequests();
    }

    function updateUnlockBadgeCount() {
      const badge = document.getElementById("unlockBadgeCount");
      if (!badge) return;
      const requests = JSON.parse(localStorage.getItem("hostel_unlock_requests") || "[]");
      const pendingCount = requests.filter(r => r.status === "PENDING").length;
      badge.innerText = pendingCount;
    }

    function hasAdminTemporaryUnlock(rector, type) {
      if (!rector) return false;
      if (rector.role === "ADMIN" || rector.name === "Nirmalswami") return true;
      const permissions = JSON.parse(localStorage.getItem("hostel_unlock_permissions") || "{}");
      const rId = String(rector.id || rector.phone || rector.name);
      if (permissions[rId] && permissions[rId][type]) {
        if (Date.now() <= permissions[rId][type]) {
          return true;
        }
      }
      return false;
    }

    /* FILTERS SETUP */
    function setupRectorStrictFilters() {
      if (!currentRector) return;

      const stdDropdown = document.getElementById("stdFilterDropdown");
      stdDropdown.innerHTML = "";
      if (currentRector.role === "ADMIN" || currentRector.role === "ALL_RECTOR" || currentRector.std === "ALL" || currentRector.name === "Nirmalswami") {
        stdDropdown.innerHTML = `
          <option value="ALL">All Standards</option>
          <option value="12">STD 12</option>
          <option value="11">STD 11</option>
          <option value="10">STD 10</option>
          <option value="9">STD 9</option>
          <option value="8">STD 8</option>
          <option value="7">STD 7</option>
        `;
      } else {
        let stdArr = Array.isArray(currentRector.std) ? currentRector.std : [currentRector.std];
        if (stdArr.length > 1) {
          stdDropdown.innerHTML = `<option value="ALL">All (STD ${stdArr.join(" & ")})</option>`;
          stdArr.forEach(st => stdDropdown.innerHTML += `<option value="${st}">STD ${st}</option>`);
        } else {
          stdDropdown.innerHTML = `<option value="${stdArr[0]}">STD ${stdArr[0]}</option>`;
        }
      }

      const medDropdown = document.getElementById("mediumFilterDropdown");
      if ((currentRector.role === "ADMIN" || currentRector.role === "ALL_RECTOR" || currentRector.name === "Nirmalswami") && currentRector.medium === "ALL") {
        medDropdown.innerHTML = `<option value="ALL">All Medium</option><option value="Gujarati">Gujarati Medium</option><option value="English">English Medium</option>`;
      } else if (currentRector.medium && currentRector.medium !== "ALL") {
        medDropdown.innerHTML = `<option value="${currentRector.medium}">${currentRector.medium} Medium</option>`;
      } else {
        medDropdown.innerHTML = `<option value="ALL">All Medium</option><option value="Gujarati">Gujarati Medium</option><option value="English">English Medium</option>`;
      }

      const studentRoomDrop = document.getElementById("studentListRoomDropdown");
      studentRoomDrop.innerHTML = `<option value="ALL">All Rooms</option>`;
      
      const assignedRooms = [];
      (window.students || []).forEach(s => {
        if (isStudentInRectorWing(s, currentRector) && s.room) {
          if (!assignedRooms.includes(String(s.room))) {
            assignedRooms.push(String(s.room));
          }
        }
      });

      assignedRooms.sort((a,b) => a.localeCompare(b, undefined, {numeric: true})).forEach(r => {
        studentRoomDrop.innerHTML += `<option value="${r}">Room No. ${r}</option>`;
      });

      filterRectorStudents();
    }

    function openRectorStudentsView() {
      document.getElementById("rectorCardsView").style.display = "none";
      document.getElementById("rectorTableView").style.display = "block";
      setupRectorStrictFilters();
    }

    function backToRectorCards() {
      document.getElementById("rectorTableView").style.display = "none";
      document.getElementById("rectorCardsView").style.display = "block";
      checkRectorApprovedPermissionsBanner();
    }

    function filterRectorStudents() {
      if (!currentRector) return;
      const query = (document.getElementById("searchBox").value || "").toLowerCase().trim();
      const selStd = document.getElementById("stdFilterDropdown").value;
      const selMed = document.getElementById("mediumFilterDropdown").value;
      const selRoom = document.getElementById("studentListRoomDropdown").value;

      const list = (window.students || []).filter(s => {
        if (!isStudentInRectorWing(s, currentRector)) return false;

        const stdNum = s.stdNumber || String(s.class || "").replace(/\D/g, "");
        const medium = s.medium || (String(s.class || "").toLowerCase().includes("th") ? "English" : "Gujarati");

        if (selStd !== "ALL" && stdNum !== selStd) return false;
        if (selMed !== "ALL" && medium !== selMed) return false;
        if (selRoom !== "ALL" && String(s.room) !== String(selRoom)) return false;

        if (query) {
          const fn = ((s.firstName || '') + ' ' + (s.surname || '')).toLowerCase();
          const fatherName = String(s.fatherName || '').toLowerCase();
          const fatherPhone = String(s.fatherPhone || s.emergencyPhone || '');
          return (fn.includes(query) || String(s.id).includes(query) || String(s.room).includes(query) || fatherName.includes(query) || fatherPhone.includes(query));
        }
        return true;
      });

      const tbody = document.getElementById("rectorStudentTbody");
      tbody.innerHTML = "";

      if (list.length === 0) {
        tbody.innerHTML = `<tr><td colspan="8" style="text-align:center; padding:15px; color:gray;">No students found</td></tr>`;
        return;
      }

      const savedAll = JSON.parse(localStorage.getItem("hostel_attendance") || "{}");

      list.forEach(s => {
        let total = 0, p = 0;
        for (let d in savedAll) {
          if (savedAll[d]) {
            if (typeof savedAll[d][s.id] === "string") {
              total++;
              if (savedAll[d][s.id] === "P") p++;
            } else if (typeof savedAll[d][s.id] === "object") {
              for (let slotKey in savedAll[d][s.id]) {
                total++;
                if (savedAll[d][s.id][slotKey].status === "P") p++;
              }
            }
          }
        }

        const pct = total > 0 ? Math.round((p / total) * 100) : 100;
        const photo = getStudentPhoto(s);
        const fPhone = s.fatherPhone || s.emergencyPhone || "-";

        tbody.innerHTML += `
          <tr>
            <td style="padding:6px; text-align:center;">
              <img src="${photo}" class="table-profile-photo" alt="Student">
            </td>
            <td style="padding:8px;">${s.id}</td>
            <td style="padding:8px;"><b>${s.firstName} ${s.surname}</b></td>
            <td style="padding:8px;">
              ${s.fatherName || '-'}<br>
              <small style="color:#1a73e8;"><a href="tel:${fPhone}" style="text-decoration:none; color:#1a73e8;">📞 ${fPhone}</a></small>
            </td>
            <td style="padding:8px;">STD ${s.stdNumber || s.class}</td>
            <td style="padding:8px; font-weight:bold;">${s.room}</td>
            <td style="padding:8px;">${s.bed}</td>
            <td style="padding:8px; text-align:center; color:${pct >= 75 ? '#0f9d58' : '#d93025'}; font-weight:bold;">${pct}%</td>
          </tr>
        `;
      });
    }

    /* ATTENDANCE */
    function getTodayDateString() {
      return new Date().toISOString().split('T')[0];
    }

    function getHolidayDates() {
      return JSON.parse(localStorage.getItem("hostel_holidays") || "[]");
    }

    function isHolidayDate(date) {
      if (!date) return false;
      const holidays = getHolidayDates();
      if (holidays.includes(date)) return true;
      const parts = date.split("-");
      if (parts.length !== 3) return false;
      const d = new Date(Number(parts[0]), Number(parts[1]) - 1, Number(parts[2]));
      return d.getDay() === 0 || d.getDay() === 6;
    }

    function toggleTodayHoliday() {
      const date = document.getElementById("attendanceDate").value;
      const checked = document.getElementById("holidayAttendanceCheck").checked;
      let holidays = getHolidayDates();
      if (checked) {
        if (!holidays.includes(date)) holidays.push(date);
      } else {
        holidays = holidays.filter(d => d !== date);
      }
      localStorage.setItem("hostel_holidays", JSON.stringify(holidays));
      loadAttendanceForDate();
    }

    function isCurrentTimeInSlot(startH, startM, endH, endM) {
      const now = new Date();
      const cur = now.getHours() * 60 + now.getMinutes();
      return (cur >= (startH * 60 + startM) && cur <= (endH * 60 + endM));
    }

    function checkAttendanceTimeSlot(student, date) {
      if (hasAdminTemporaryUnlock(currentRector, "ATTENDANCE")) {
        return { allowed: true, slotName: "Special Slot (Admin Unlocked)" };
      }

      if (isHolidayDate(date)) {
        if (isCurrentTimeInSlot(7, 45, 8, 0)) return { allowed: true, slotName: "Holiday Morning (7:45 - 8:00 AM)" };
        if (isCurrentTimeInSlot(10, 0, 10, 30)) return { allowed: true, slotName: "Holiday Morning (10:00 - 10:30 AM)" };
        if (isCurrentTimeInSlot(12, 30, 13, 30)) return { allowed: true, slotName: "Holiday Sleeping Bell (12:30 - 1:30 PM)" };
        if (isCurrentTimeInSlot(15, 0, 15, 45)) return { allowed: true, slotName: "Holiday Afternoon (3:00 - 3:45 PM)" };
        if (isCurrentTimeInSlot(17, 0, 17, 30)) return { allowed: true, slotName: "Holiday Evening (5:00 - 5:30 PM)" };
        if (isCurrentTimeInSlot(20, 30, 21, 0)) return { allowed: true, slotName: "Holiday Night (8:30 - 9:00 PM)" };
        return { allowed: false, message: "Holiday window closed" };
      }

      if (isCurrentTimeInSlot(12, 30, 13, 30)) return { allowed: true, slotName: "Sleeping Bell (12:30 to 1:30 PM)" };

      const stdNum = String(student.stdNumber || student.class || "").replace(/\D/g, "");
      const medium = student.medium || (String(student.class || "").toLowerCase().includes("th") ? "English" : "Gujarati");

      if (medium === "English") {
        if (isCurrentTimeInSlot(13, 0, 13, 30)) return { allowed: true, slotName: "Afternoon (1:00 to 1:30 PM)" };
        if (isCurrentTimeInSlot(17, 0, 17, 30)) return { allowed: true, slotName: "Evening (5:00 to 5:30 PM)" };
        if (isCurrentTimeInSlot(20, 30, 21, 15)) return { allowed: true, slotName: "Night (8:30 to 9:15 PM)" };
        return { allowed: false, message: "Attendance closed" };
      }

      if (medium === "Gujarati") {
        if (stdNum === "7" || stdNum === "8") {
          if (isCurrentTimeInSlot(10, 0, 10, 30)) return { allowed: true, slotName: "Morning (10:00 to 10:30 AM)" };
          if (isCurrentTimeInSlot(17, 30, 17, 45)) return { allowed: true, slotName: "After School (5:30 to 5:45 PM)" };
          if (isCurrentTimeInSlot(20, 30, 21, 15)) return { allowed: true, slotName: "Night (8:30 to 9:15 PM)" };
          return { allowed: false, message: "Attendance closed" };
        }
        if (stdNum === "9" || stdNum === "10") {
          if (isCurrentTimeInSlot(13, 0, 13, 15)) return { allowed: true, slotName: "Afternoon (1:00 to 1:15 PM)" };
          if (isCurrentTimeInSlot(17, 0, 17, 30)) return { allowed: true, slotName: "Evening (5:00 to 5:30 PM)" };
          if (isCurrentTimeInSlot(20, 30, 21, 15)) return { allowed: true, slotName: "Night (8:30 to 9:15 PM)" };
          return { allowed: false, message: "Attendance closed" };
        }
        if (stdNum === "11" || stdNum === "12") {
          if (isCurrentTimeInSlot(17, 0, 17, 30)) return { allowed: true, slotName: "Evening (5:00 to 5:30 PM)" };
          if (isCurrentTimeInSlot(20, 30, 21, 15)) return { allowed: true, slotName: "Night (8:30 to 9:15 PM)" };
          return { allowed: false, message: "Attendance closed" };
        }
      }
      return { allowed: false, message: "Attendance closed" };
    }

    function isNightCheckTimeSlot() {
      if (hasAdminTemporaryUnlock(currentRector, "NIGHT_CHECK")) {
        return true;
      }
      return isCurrentTimeInSlot(22, 15, 23, 0);
    }

    function openRectorAttendance() {
      document.getElementById("rectorCardsView").style.display = "none";
      document.getElementById("rectorAttendanceView").style.display = "block";
      currentAttendanceData = {};
      currentAttendanceReasons = {};
      currentAttViewStatusFilter = "ALL";
      const today = getTodayDateString();
      document.getElementById("attendanceDate").value = today;
      document.getElementById("holidayAttendanceCheck").checked = isHolidayDate(today);

      const stdDrop = document.getElementById("attStdFilterDropdown");
      stdDrop.innerHTML = `<option value="ALL">All Standards</option><option value="12">STD 12</option><option value="11">STD 11</option><option value="10">STD 10</option><option value="9">STD 9</option><option value="8">STD 8</option><option value="7">STD 7</option>`;

      const roomDrop = document.getElementById("attRoomFilterDropdown");
      roomDrop.innerHTML = `<option value="ALL">All Rooms</option>`;
      const rooms = [];
      (window.students || []).forEach(s => {
        if (isStudentInRectorWing(s, currentRector) && s.room && !rooms.includes(String(s.room))) {
          rooms.push(String(s.room));
        }
      });
      rooms.sort((a,b) => a.localeCompare(b, undefined, {numeric: true})).forEach(r => roomDrop.innerHTML += `<option value="${r}">Room No. ${r}</option>`);

      document.getElementById("attSearchBox").value = "";
      updateAttendanceFilterButtonsUI();
      loadAttendanceForDate();
    }

    function backFromAttendance() {
      document.getElementById("rectorAttendanceView").style.display = "none";
      document.getElementById("rectorCardsView").style.display = "block";
    }

    function filterAttendanceStatus(status) {
      currentAttViewStatusFilter = status;
      updateAttendanceFilterButtonsUI();
      loadAttendanceForDate();
    }

    function updateAttendanceFilterButtonsUI() {
      const bAll = document.getElementById("attFilterAll");
      const bPres = document.getElementById("attFilterPresent");
      const bAbs = document.getElementById("attFilterAbsent");

      bAll.className = "status-filter-btn" + (currentAttViewStatusFilter === "ALL" ? " active-all" : "");
      bPres.className = "status-filter-btn" + (currentAttViewStatusFilter === "PRESENT" ? " active-present" : "");
      bAbs.className = "status-filter-btn" + (currentAttViewStatusFilter === "ABSENT" ? " active-absent" : "");
    }

    function loadAttendanceForDate() {
      const date = document.getElementById("attendanceDate").value;
      const holidayCheck = document.getElementById("holidayAttendanceCheck");
      if (holidayCheck) holidayCheck.checked = isHolidayDate(date);

      const tbody = document.getElementById("attendanceTbody");
      tbody.innerHTML = "";
      const query = (document.getElementById("attSearchBox").value || "").toLowerCase().trim();
      const selStd = document.getElementById("attStdFilterDropdown").value;
      const selMed = document.getElementById("attMediumFilterDropdown").value;
      const roomFilter = document.getElementById("attRoomFilterDropdown").value;

      const savedAll = JSON.parse(localStorage.getItem("hostel_attendance") || "{}");
      const dayRec = savedAll[date] || {};
      const isToday = date === getTodayDateString();

      const list = (window.students || []).filter(s => {
        if (!isStudentInRectorWing(s, currentRector)) return false;

        const stdNum = s.stdNumber || String(s.class || "").replace(/\D/g, "");
        const medium = s.medium || (String(s.class || "").toLowerCase().includes("th") ? "English" : "Gujarati");

        if (selStd !== "ALL" && stdNum !== selStd) return false;
        if (selMed !== "ALL" && medium !== selMed) return false;
        if (roomFilter !== "ALL" && String(s.room) !== String(roomFilter)) return false;

        if (query) {
          const fn = ((s.firstName || '') + ' ' + (s.surname || '')).toLowerCase();
          return (fn.includes(query) || String(s.id).includes(query) || String(s.room).includes(query));
        }
        return true;
      });

      const saveBtn = document.getElementById("saveAttendanceBtn");
      const unlockBtn = document.getElementById("requestUnlockAttBtn");
      let canEditAny = false;
      let renderedRowsCount = 0;

      list.forEach(s => {
        let existingStatus = currentAttendanceData[s.id] || "P";
        let existingReason = currentAttendanceReasons[s.id] || "";

        if (currentAttendanceData[s.id] === undefined && dayRec[s.id]) {
          if (typeof dayRec[s.id] === "string") {
            existingStatus = dayRec[s.id];
          } else if (typeof dayRec[s.id] === "object") {
            const timeCheckCurrent = checkAttendanceTimeSlot(s, date);
            const slotKey = timeCheckCurrent.slotName || "General";
            if (dayRec[s.id][slotKey]) {
              existingStatus = dayRec[s.id][slotKey].status || "P";
              existingReason = dayRec[s.id][slotKey].reason || "";
            }
          }
        }

        currentAttendanceData[s.id] = existingStatus;
        currentAttendanceReasons[s.id] = existingReason;

        if (currentAttViewStatusFilter === "PRESENT" && existingStatus !== "P") return;
        if (currentAttViewStatusFilter === "ABSENT" && existingStatus !== "A") return;

        renderedRowsCount++;
        const isP = (existingStatus === "P");
        const timeCheck = checkAttendanceTimeSlot(s, date);
        const canEdit = isToday && timeCheck.allowed;
        if (canEdit) canEditAny = true;
        const fPhone = s.fatherPhone || s.emergencyPhone || "";

        const actionBtns = canEdit ? `
          <div style="display:flex; flex-direction:column; align-items:center; gap:4px;">
            <div style="display:flex; gap:4px;">
              <button type="button" id="btn_P_${s.id}" onclick="setAttendanceStatus('${s.id}', 'P')" style="width:auto; padding:5px 12px; font-weight:bold; border-radius:4px; background:${isP ? '#0f9d58' : '#f1f3f4'}; color:${isP ? 'white' : '#333'};">P</button>
              <button type="button" id="btn_A_${s.id}" onclick="setAttendanceStatus('${s.id}', 'A')" style="width:auto; padding:5px 12px; font-weight:bold; border-radius:4px; background:${!isP ? '#d93025' : '#f1f3f4'}; color:${!isP ? 'white' : '#333'};">A</button>
            </div>
            <input type="text" id="att_reason_${s.id}" placeholder="ક્યાં ગયો છે? કારણ લખો..." value="${existingReason}" oninput="setAttendanceReason('${s.id}', this.value)" style="display:${isP ? 'none' : 'block'}; width:180px; padding:4px 8px; font-size:12px; margin:4px 0 0 0; border:1px solid #d93025; border-radius:4px;">
            <div id="att_wa_${s.id}" style="display:${!isP && fPhone ? 'block' : 'none'}; margin-top:4px;">
              <button type="button" onclick="sendAbsentWhatsAppToParent('${s.firstName} ${s.surname}', '${s.room}', '${fPhone}', '${existingReason || 'હાજર નથી'}')" style="width:auto; padding:3px 8px; font-size:11px; background:#25d366; color:white; border-radius:4px;">
                📲 વાલીને WhatsApp
              </button>
            </div>
          </div>
        ` : `
          <span style="padding:4px 8px; border-radius:4px; font-weight:bold; font-size:12px; background:${isP ? '#e6f4ea' : '#fce8e6'}; color:${isP ? '#137333' : '#d93025'};">
            ${isP ? 'Present (P)' : 'Absent (A)'}
          </span>
          ${(!isP && existingReason) ? `<small style="display:block; color:#d93025; font-size:11px; margin-top:3px;">કારણ: <b>${existingReason}</b></small>` : ''}
          <small style="display:block; color:#d93025; font-size:10px;">${!isToday ? 'Date Locked' : timeCheck.message}</small>
        `;

        tbody.innerHTML += `
          <tr>
            <td style="padding:8px;">${s.id}</td>
            <td style="padding:8px;"><b>${s.firstName} ${s.surname}</b></td>
            <td style="padding:8px;">STD ${s.stdNumber || s.class}</td>
            <td style="padding:8px;">${s.room}</td>
            <td style="padding:8px; text-align:center;">${actionBtns}</td>
          </tr>
        `;
      });

      if (renderedRowsCount === 0) {
        tbody.innerHTML = `<tr><td colspan="5" style="text-align:center; padding:15px; color:gray;">No students matching current filter</td></tr>`;
      }

      if (canEditAny) {
        saveBtn.disabled = false;
        saveBtn.style.background = "#0f9d58";
        saveBtn.innerText = "SAVE ATTENDANCE";
        if (unlockBtn) unlockBtn.style.display = "none";
      } else {
        saveBtn.disabled = true;
        saveBtn.innerText = "SAVE ATTENDANCE (LOCKED - TIME CLOSED)";
        if (unlockBtn && isToday && currentRector.role !== "ADMIN" && currentRector.name !== "Nirmalswami") {
          unlockBtn.style.display = "block";
        } else if (unlockBtn) {
          unlockBtn.style.display = "none";
        }
      }
    }

    function setAttendanceStatus(id, st) {
      currentAttendanceData[id] = st;
      const p = document.getElementById("btn_P_" + id);
      const a = document.getElementById("btn_A_" + id);
      const rBox = document.getElementById("att_reason_" + id);
      const waBox = document.getElementById("att_wa_" + id);

      if (st === "P") {
        if (p) { p.style.background = "#0f9d58"; p.style.color = "white"; }
        if (a) { a.style.background = "#f1f3f4"; a.style.color = "#333"; }
        if (rBox) { rBox.style.display = "none"; rBox.value = ""; }
        if (waBox) waBox.style.display = "none";
        currentAttendanceReasons[id] = "";
      } else {
        if (a) { a.style.background = "#d93025"; a.style.color = "white"; }
        if (p) { p.style.background = "#f1f3f4"; p.style.color = "#333"; }
        if (rBox) { rBox.style.display = "block"; rBox.focus(); }
        if (waBox) waBox.style.display = "block";
      }
    }

    function setAttendanceReason(id, reason) {
      currentAttendanceReasons[id] = reason;
    }

    function sendAbsentWhatsAppToParent(studentName, room, phone, reason) {
      if (!phone) { alert("વાલીનો નંબર ઉપલબ્ધ નથી!"); return; }
      let p = phone.replace(/\D/g, "");
      if (p.length === 10) p = "91" + p;
      const msg = `જય સ્વામિનારાયણ.%0A%0Aધર્મજીવન છાત્રાલય તરફથી નમ્ર જાણ કે આપનો દીકરો *${studentName}* (રૂમ નં. ${room}) આજની હોસ્ટેલ હાજરીમાં *ગેરહાજર* નોંધાયેલ છે.%0Aવિગત / કારણ: ${reason}%0Aવધુ માહિતી માટે હોસ્ટેલ ઑફિસનો સંપર્ક કરવો.`;
      window.open(`https://wa.me/${p}?text=${msg}`, "_blank");
    }

    function saveAttendance() {
      const date = document.getElementById("attendanceDate").value;
      const today = getTodayDateString();

      if (date !== today) {
        alert("Only today's attendance can be edited!");
        return;
      }

      const all = JSON.parse(localStorage.getItem("hostel_attendance") || "{}");
      if (!all[date]) all[date] = {};

      const nowTime = new Date().toLocaleTimeString("en-US", { hour: '2-digit', minute: '2-digit' });

      for (let sId in currentAttendanceData) {
        const studentObj = (window.students || []).find(st => String(st.id) === String(sId));
        const timeSlotObj = studentObj ? checkAttendanceTimeSlot(studentObj, date) : { allowed: true, slotName: "Slot Attendance" };
        const activeSlot = timeSlotObj.slotName || "General Slot";

        if (typeof all[date][sId] !== "object" || all[date][sId] === null) {
          all[date][sId] = {};
        }

        all[date][sId][activeSlot] = {
          status: currentAttendanceData[sId],
          reason: currentAttendanceReasons[sId] || "",
          time: nowTime,
          rector: currentRector.name
        };
      }

      localStorage.setItem("hostel_attendance", JSON.stringify(all));
      alert("Attendance saved successfully!");
      document.getElementById("attWhatsAppShareArea").style.display = "block";
    }

    function sendAdminAttendanceSummary(type) {
      const date = getTodayDateString();
      let absentees = [];

      if (type === "ATTENDANCE") {
        for (let sId in currentAttendanceData) {
          if (currentAttendanceData[sId] === "A") {
            const st = (window.students || []).find(s => String(s.id) === String(sId));
            absentees.push({
              name: st ? (st.firstName + " " + st.surname) : sId,
              room: st ? st.room : "-",
              reason: currentAttendanceReasons[sId] || "કારણ લખેલ નથી"
            });
          }
        }
      } else {
        for (let sId in currentNightCheckData) {
          if (currentNightCheckData[sId] === "ABSENT") {
            const st = (window.students || []).find(s => String(s.id) === String(sId));
            absentees.push({
              name: st ? (st.firstName + " " + st.surname) : sId,
              room: st ? st.room : "-",
              reason: currentNightCheckReasons[sId] || "કારણ લખેલ નથી"
            });
          }
        }
      }

      if (absentees.length === 0) {
        alert("આજના રાઉન્ડમાં કોઈ ગેરહાજર નથી! સૌ હાજર છે.");
        return;
      }

      // રૂમ-વાઈઝ સોર્ટિંગ
      absentees.sort((a,b) => String(a.room).localeCompare(String(b.room), undefined, {numeric: true}));

      let listText = "";
      absentees.forEach(a => {
        listText += `%0A• *રૂમ ${a.room}*: ${a.name} (કારણ: ${a.reason})`;
      });

      const title = (type === "ATTENDANCE") ? "હાજરી ગેરહાજર રિપોર્ટ" : "નાઇટ ચેક ગેરહાજર રિપોર્ટ";
      const fullMsg = `*${title} (Dharmjivan Chhatralay)*%0A*તારીખ:* ${date}%0A*રેક્ટર:* ${currentRector.name}%0A*કુલ ગેરહાજર:* ${absentees.length}%0A${listText}`;

      window.open(`https://wa.me/${ADMIN_WHATSAPP_NUMBER}?text=${fullMsg}`, "_blank");
    }

    /* NIGHT CHECK */
    function openRectorNightCheckView() {
      document.getElementById("rectorCardsView").style.display = "none";
      document.getElementById("rectorNightCheckView").style.display = "block";
      currentNightCheckData = {};
      currentNightCheckReasons = {};
      currentNcViewStatusFilter = "ALL";
      const today = getTodayDateString();
      document.getElementById("nightCheckDate").value = today;
      document.getElementById("nightCheckSearchInput").value = "";

      const roomSelect = document.getElementById("nightCheckRoomSelect");
      roomSelect.innerHTML = "";
      const rooms = [];
      (window.students || []).forEach(s => {
        if (isStudentInRectorWing(s, currentRector) && s.room && !rooms.includes(String(s.room))) {
          rooms.push(String(s.room));
        }
      });
      rooms.sort((a,b) => a.localeCompare(b, undefined, {numeric: true})).forEach(r => {
        roomSelect.innerHTML += `<option value="${r}">Room No. ${r}</option>`;
      });

      updateNightCheckFilterButtonsUI();
      loadNightCheckForRoom();
    }

    function backFromNightCheck() {
      document.getElementById("rectorNightCheckView").style.display = "none";
      document.getElementById("rectorCardsView").style.display = "block";
    }

    function filterNightCheckStatus(status) {
      currentNcViewStatusFilter = status;
      updateNightCheckFilterButtonsUI();
      loadNightCheckForRoom();
    }

    function updateNightCheckFilterButtonsUI() {
      const bAll = document.getElementById("ncFilterAll");
      const bPres = document.getElementById("ncFilterPresent");
      const bAbs = document.getElementById("ncFilterAbsent");

      bAll.className = "status-filter-btn" + (currentNcViewStatusFilter === "ALL" ? " active-all" : "");
      bPres.className = "status-filter-btn" + (currentNcViewStatusFilter === "PRESENT" ? " active-present" : "");
      bAbs.className = "status-filter-btn" + (currentNcViewStatusFilter === "ABSENT" ? " active-absent" : "");
    }

    function loadNightCheckForRoom() {
      const room = document.getElementById("nightCheckRoomSelect").value;
      const date = document.getElementById("nightCheckDate").value;
      const search = (document.getElementById("nightCheckSearchInput").value || "").toLowerCase().trim();
      const container = document.getElementById("nightCheckStudentsContainer");
      const saveBtn = document.getElementById("saveNightCheckBtn");
      const unlockNightBtn = document.getElementById("requestUnlockNightBtn");

      if (!room) {
        container.innerHTML = '<p style="color:gray;">Select room</p>';
        return;
      }

      const allChecks = JSON.parse(localStorage.getItem("hostel_night_checks") || "{}");
      const dayRec = (allChecks[date] && allChecks[date][room]) ? allChecks[date][room] : {};
      
      let roomStudents = (window.students || []).filter(s => String(s.room) === String(room) && isStudentInRectorWing(s, currentRector));

      if (search) {
        roomStudents = roomStudents.filter(s => {
          const fullName = ((s.firstName || '') + ' ' + (s.surname || '')).toLowerCase();
          const fatherPhone = String(s.fatherPhone || s.emergencyPhone || '');
          return (fullName.includes(search) || String(s.id).includes(search) || fatherPhone.includes(search));
        });
      }

      const isToday = date === getTodayDateString();
      const canEdit = isToday && isNightCheckTimeSlot();
      let renderedCount = 0;

      let html = `
        <div style="overflow-x:auto;">
          <table border="1" style="width:100%; border-collapse:collapse; background:white; font-size:14px;">
            <thead style="background:#f1f3f4;">
              <tr>
                <th style="padding:8px;">Student Details</th>
                <th style="padding:8px; text-align:center;">Night Status & Reason</th>
              </tr>
            </thead>
            <tbody>
      `;

      roomStudents.forEach(s => {
        let st = currentNightCheckData[s.id] || "PRESENT";
        let rs = currentNightCheckReasons[s.id] || "";

        if (currentNightCheckData[s.id] === undefined && dayRec.students && dayRec.students[s.id]) {
          if (typeof dayRec.students[s.id] === "string") {
            st = dayRec.students[s.id];
          } else if (typeof dayRec.students[s.id] === "object") {
            st = dayRec.students[s.id].status || "PRESENT";
            rs = dayRec.students[s.id].reason || "";
          }
        }

        currentNightCheckData[s.id] = st;
        currentNightCheckReasons[s.id] = rs;

        if (currentNcViewStatusFilter === "PRESENT" && st !== "PRESENT") return;
        if (currentNcViewStatusFilter === "ABSENT" && st !== "ABSENT") return;

        renderedCount++;
        const isOk = (st === "PRESENT");
        const fPhone = s.fatherPhone || s.emergencyPhone || "";

        const actionBtns = canEdit ? `
          <div style="display:flex; flex-direction:column; align-items:center; gap:4px;">
            <div style="display:flex; gap:4px;">
              <button type="button" id="nc_p_${s.id}" onclick="setNightCheckStatus('${s.id}', 'PRESENT')" style="width:auto; padding:5px 10px; font-size:12px; background:${isOk ? '#0f9d58' : '#e0e0e0'}; color:${isOk ? 'white' : 'black'};">Present</button>
              <button type="button" id="nc_a_${s.id}" onclick="setNightCheckStatus('${s.id}', 'ABSENT')" style="width:auto; padding:5px 10px; font-size:12px; background:${!isOk ? '#d93025' : '#e0e0e0'}; color:${!isOk ? 'white' : 'black'};">Absent</button>
            </div>
            <input type="text" id="nc_reason_${s.id}" placeholder="ક્યાં ગયો છે? કારણ લખો..." value="${rs}" oninput="setNightCheckReason('${s.id}', this.value)" style="display:${isOk ? 'none' : 'block'}; width:180px; padding:4px 8px; font-size:12px; margin:4px 0 0 0; border:1px solid #d93025; border-radius:4px;">
            <div id="nc_wa_${s.id}" style="display:${!isOk && fPhone ? 'block' : 'none'}; margin-top:4px;">
              <button type="button" onclick="sendAbsentWhatsAppToParent('${s.firstName} ${s.surname}', '${s.room}', '${fPhone}', '${rs || 'નાઇટ રાઉન્ડમાં ગેરહાજર'}')" style="width:auto; padding:3px 8px; font-size:11px; background:#25d366; color:white; border-radius:4px;">
                📲 વાલીને WhatsApp
              </button>
            </div>
          </div>
        ` : `
          <span style="padding:4px 8px; border-radius:4px; font-weight:bold; font-size:12px; background:${isOk ? '#e6f4ea' : '#fce8e6'}; color:${isOk ? '#137333' : '#d93025'};">${isOk ? 'Present (OK)' : 'Absent'}</span>
          ${(!isOk && rs) ? `<small style="display:block; color:#d93025; font-size:11px; margin-top:3px;">કારણ: <b>${rs}</b></small>` : ''}
          <small style="display:block; color:#d93025; font-size:10px;">${!isToday ? 'Date Locked' : 'Locked (10:15 - 11:00 PM)'}</small>
        `;

        html += `
          <tr>
            <td style="padding:10px;">
              <b>${s.firstName || ''} ${s.surname || ''}</b> (HR No: ${s.id || '-'}/Bed: ${s.bed || '-'})<br>
              <small style="color:#555;">P: <a href="tel:${fPhone}" style="color:#1a73e8; text-decoration:none;">${fPhone || '-'}</a></small>
            </td>
            <td style="padding:8px; text-align:center;">${actionBtns}</td>
          </tr>
        `;
      });

      if (renderedCount === 0) {
        html += `<tr><td colspan="2" style="padding:20px; text-align:center; color:gray;">No students matching filter in this room</td></tr>`;
      }

      html += `</tbody></table></div>`;
      container.innerHTML = html;
      document.getElementById("nightCheckRoomRemark").value = dayRec.remark || "";
      document.getElementById("nightCheckRoomRemark").disabled = !canEdit;

      if (canEdit) {
        saveBtn.disabled = false;
        saveBtn.style.background = "#0f9d58";
        saveBtn.innerText = "SAVE ROOM CHECKING";
        if (unlockNightBtn) unlockNightBtn.style.display = "none";
      } else {
        saveBtn.disabled = true;
        saveBtn.innerText = "SAVE ROOM CHECKING (LOCKED - 10:15 TO 11:00 PM)";
        if (unlockNightBtn && isToday && currentRector.role !== "ADMIN" && currentRector.name !== "Nirmalswami") {
          unlockNightBtn.style.display = "block";
        } else if (unlockNightBtn) {
          unlockNightBtn.style.display = "none";
        }
      }
    }

    function setNightCheckStatus(id, st) {
      currentNightCheckData[id] = st;
      const p = document.getElementById("nc_p_" + id);
      const a = document.getElementById("nc_a_" + id);
      const rBox = document.getElementById("nc_reason_" + id);
      const waBox = document.getElementById("nc_wa_" + id);

      if (st === "PRESENT") {
        if (p) { p.style.background = "#0f9d58"; p.style.color = "white"; }
        if (a) { a.style.background = "#e0e0e0"; a.style.color = "black"; }
        if (rBox) { rBox.style.display = "none"; rBox.value = ""; }
        if (waBox) waBox.style.display = "none";
        currentNightCheckReasons[id] = "";
      } else {
        if (a) { a.style.background = "#d93025"; a.style.color = "white"; }
        if (p) { p.style.background = "#e0e0e0"; p.style.color = "black"; }
        if (rBox) { rBox.style.display = "block"; rBox.focus(); }
        if (waBox) waBox.style.display = "block";
      }
    }

    function setNightCheckReason(id, reason) {
      currentNightCheckReasons[id] = reason;
    }

    function saveNightCheckReport() {
      const room = document.getElementById("nightCheckRoomSelect").value;
      const date = document.getElementById("nightCheckDate").value;
      const remark = document.getElementById("nightCheckRoomRemark").value.trim();

      if (!room || !date) { alert("Please select date and room!"); return; }
      if (date !== getTodayDateString()) { alert("Only today's night check can be saved!"); return; }
      if (!isNightCheckTimeSlot()) { alert("Allowed time: 10:15 PM to 11:00 PM."); return; }

      const allChecks = JSON.parse(localStorage.getItem("hostel_night_checks") || "{}");
      if (!allChecks[date]) allChecks[date] = {};
      const existingRoomData = allChecks[date][room] || {};
      const oldStudents = existingRoomData.students || {};

      const formattedStudents = {};
      for (let sId in currentNightCheckData) {
        formattedStudents[sId] = {
          status: currentNightCheckData[sId],
          reason: currentNightCheckReasons[sId] || ""
        };
      }

      const mergedStudents = Object.assign({}, oldStudents, formattedStudents);

      allChecks[date][room] = {
        checkedBy: currentRector.name,
        time: new Date().toLocaleTimeString("en-US", { hour: '2-digit', minute: '2-digit' }),
        students: mergedStudents,
        remark: remark
      };

      localStorage.setItem("hostel_night_checks", JSON.stringify(allChecks));
      alert("Room No. " + room + " night check record saved successfully!");
      document.getElementById("ncWhatsAppShareArea").style.display = "block";
      loadNightCheckForRoom();
    }

    /* SMART WORK & COMPLAINTS SYSTEM (WITH PHOTO UPLOAD) */
    function switchRecordTab(tab) {
      activeRecordTab = tab;
      const smartTab = document.getElementById("tabSmartWorkBtn");
      const compTab = document.getElementById("tabComplaintBtn");
      const formTitle = document.getElementById("recordFormTitle");
      const submitBtn = document.getElementById("submitRecordBtn");
      const typeSelect = document.getElementById("complaintTypeSelect");

      if (tab === "SMARTWORK") {
        smartTab.className = "tab-btn tab-active-smart";
        compTab.className = "tab-btn";
        formTitle.innerText = "Add Smart Work Record (Sari Pravrutti / Positive)";
        formTitle.style.color = "#0f9d58";
        submitBtn.style.background = "#0f9d58";
        submitBtn.innerText = "SUBMIT SMART WORK";

        typeSelect.innerHTML = `
          <option value="Academic Excellence">Academic Excellence (સારો અભ્યાસ)</option>
          <option value="Good Discipline">Good Discipline (ઉત્તમ શિસ્ત)</option>
          <option value="Hostel Seva / Help">Hostel Seva / Help (હોસ્ટેલ સેવા)</option>
          <option value="Cleanliness Leader">Cleanliness Leader (સ્વચ્છતા)</option>
          <option value="Cultural / Sports Activity">Cultural / Sports Activity</option>
          <option value="Other Positive">Other Positive Work</option>
        `;
      } else {
        compTab.className = "tab-btn tab-active-complaint";
        smartTab.className = "tab-btn";
        formTitle.innerText = "Add Complaint Record (Fariyad / Negative)";
        formTitle.style.color = "#d93025";
        submitBtn.style.background = "#d93025";
        submitBtn.innerText = "SUBMIT COMPLAINT";

        typeSelect.innerHTML = `
          <option value="Discipline Issue">Discipline Issue</option>
          <option value="Study Irregularity">Study Irregularity</option>
          <option value="Hostel Rule Violation">Hostel Rule Violation</option>
          <option value="Late Arrival">Late Arrival</option>
          <option value="Cleanliness Issue">Cleanliness Issue</option>
          <option value="Other Violation">Other</option>
        `;
      }

      loadSelectedStudentComplaints();
    }

    function openRectorComplaintView() {
      document.getElementById("rectorCardsView").style.display = "none";
      document.getElementById("rectorComplaintView").style.display = "block";
      filterComplaintStudents();
      switchRecordTab("SMARTWORK");
    }

    function backFromComplaint() {
      document.getElementById("rectorComplaintView").style.display = "none";
      document.getElementById("rectorCardsView").style.display = "block";
    }

    function filterComplaintStudents() {
      const query = (document.getElementById("complaintSearchInput").value || "").toLowerCase().trim();
      const select = document.getElementById("complaintStudentSelect");
      select.innerHTML = '<option value="">-- Select Student (HR No / Name) --</option>';

      (window.students || []).filter(s => {
        if (!isStudentInRectorWing(s, currentRector)) return false;

        if (query) {
          const fn = ((s.firstName || '') + ' ' + (s.surname || '')).toLowerCase();
          return (fn.includes(query) || String(s.id).includes(query) || String(s.room).includes(query));
        }
        return true;
      }).forEach(s => {
        select.innerHTML += `<option value="${s.id}">${s.firstName} ${s.surname} (HR No: ${s.id} | Room: ${s.room})</option>`;
      });
    }

    function onComplaintStudentChanged() {
      loadSelectedStudentComplaints();
    }

    function submitStudentRecord() {
      const studentId = document.getElementById("complaintStudentSelect").value;
      const type = document.getElementById("complaintTypeSelect").value;
      const detail = document.getElementById("complaintDetailInput").value.trim();
      const fileInput = document.getElementById("recordImageInput");

      if (!studentId || !detail) { alert("Please select student and write details!"); return; }

      const st = (window.students || []).find(s => String(s.id) === String(studentId));
      const complaints = JSON.parse(localStorage.getItem("hostel_complaints") || "[]");
      const currentRectorId = String(currentRector.id || currentRector.phone || currentRector.name || "");

      function saveRecord(photoData) {
        complaints.unshift({
          id: Date.now(),
          category: activeRecordTab,
          studentId: studentId,
          studentName: st ? (st.firstName + " " + st.surname) : "Student",
          studentRoom: st ? st.room : "-",
          rectorName: currentRector.name,
          rectorId: currentRectorId,
          type: type,
          detail: detail,
          photo: photoData || "",
          date: new Date().toLocaleDateString("en-US")
        });

        localStorage.setItem("hostel_complaints", JSON.stringify(complaints));
        alert(activeRecordTab === "SMARTWORK" ? "Smart work entry submitted!" : "Complaint submitted!");
        document.getElementById("complaintDetailInput").value = "";
        if (fileInput) fileInput.value = "";
        loadSelectedStudentComplaints();
      }

      if (fileInput && fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = function(e) {
          saveRecord(e.target.result);
        };
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        saveRecord("");
      }
    }

    function loadSelectedStudentComplaints() {
      const container = document.getElementById("rectorComplaintListContainer");
      const headerEl = document.getElementById("complaintListHeader");
      const selectedStudentId = document.getElementById("complaintStudentSelect").value;
      const complaints = JSON.parse(localStorage.getItem("hostel_complaints") || "[]");

      const isAdmin = (currentRector.role === "ADMIN" || currentRector.name === "Nirmalswami");

      let filteredComplaints = [];

      const tabSpecificComplaints = complaints.filter(c => {
        const cat = c.category || "COMPLAINT";
        return cat === activeRecordTab;
      });

      if (isAdmin) {
        headerEl.innerText = activeRecordTab === "SMARTWORK" 
          ? "All Smart Work Entries (Admin Master View):" 
          : "All Complaints (Admin Master View):";
        if (selectedStudentId) {
          filteredComplaints = tabSpecificComplaints.filter(c => String(c.studentId) === String(selectedStudentId));
        } else {
          filteredComplaints = tabSpecificComplaints;
        }
      } else {
        if (!selectedStudentId) {
          container.innerHTML = `<p style="color:gray; padding:15px; text-align:center;">Select a student from dropdown above to view records.</p>`;
          headerEl.innerText = "Select a Student to View Records:";
          return;
        }
        headerEl.innerText = `${activeRecordTab === 'SMARTWORK' ? 'Smart Work' : 'Complaints'} for Selected Student:`;
        filteredComplaints = tabSpecificComplaints.filter(c => String(c.studentId) === String(selectedStudentId));
      }

      if (filteredComplaints.length === 0) {
        container.innerHTML = `<p style="color:gray; padding:10px;">No records found.</p>`;
        return;
      }

      const activeRectorKey = String(currentRector.id || currentRector.phone || currentRector.name || "");
      let html = "";

      filteredComplaints.forEach(c => {
        const isAuthor = (c.rectorId && String(c.rectorId) === activeRectorKey) || (!c.rectorId && c.rectorName === currentRector.name);
        const canDelete = isAuthor || isAdmin;
        const isSmart = (c.category === "SMARTWORK");

        const deleteBtnHtml = canDelete
          ? `<button type="button" onclick="deleteComplaint(${c.id})" style="width:auto; padding:5px 9px; font-size:11px; background:#d93025; margin:0;">🗑️ Delete</button>`
          : `<span style="font-size:11px; color:gray; background:#f1f3f4; padding:3px 6px; border-radius:4px;">🔒 Read Only</span>`;

        html += `
          <div class="${isSmart ? 'smartwork-card' : 'complaint-card'}">
            <div style="display:flex; justify-content:space-between; align-items:center;">
              <div>
                <b style="font-size:14px; color:${isSmart ? '#0f9d58' : '#d93025'};">${c.studentName} (HR: ${c.studentId} | Room: ${c.studentRoom || '-'})</b>
                <span style="background:${isSmart ? '#e6f4ea' : '#fce8e6'}; color:${isSmart ? '#137333' : '#d93025'}; padding:2px 8px; border-radius:4px; font-weight:bold; font-size:11px; margin-left:6px;">${c.type}</span>
              </div>
              <small style="color:gray;">${c.date}</small>
            </div>
            <p style="margin:8px 0; font-size:14px; color:#333;">${c.detail}</p>
            ${c.photo ? `<img src="${c.photo}" style="max-width:100%; max-height:220px; border-radius:8px; margin:6px 0; border:1px solid #ddd;" alt="Record Attachment">` : ''}
            <div style="display:flex; justify-content:space-between; align-items:center; gap:8px;">
              <small style="color:#666;">By: <b>${c.rectorName}</b></small>
              ${deleteBtnHtml}
            </div>
          </div>
        `;
      });
      container.innerHTML = html;
    }

    function deleteComplaint(id) {
      let complaints = JSON.parse(localStorage.getItem("hostel_complaints") || "[]");
      const complaint = complaints.find(c => Number(c.id) === Number(id));
      if (!complaint) return;

      const activeRectorKey = String(currentRector.id || currentRector.phone || currentRector.name || "");
      const isAuthor = (complaint.rectorId && String(complaint.rectorId) === activeRectorKey) || (!complaint.rectorId && complaint.rectorName === currentRector.name);
      const canDelete = isAuthor || (currentRector.role === "ADMIN" || currentRector.name === "Nirmalswami");

      if (!canDelete) {
        alert("This record can only be deleted by " + complaint.rectorName + " or Admin!");
        return;
      }

      if (!confirm("Are you sure you want to delete this record?")) return;
      complaints = complaints.filter(c => Number(c.id) !== Number(id));
      localStorage.setItem("hostel_complaints", JSON.stringify(complaints));
      alert("Record deleted successfully!");
      loadSelectedStudentComplaints();
    }

    /* NOTICE BOARD */
    function openRectorNoticeView() {
      document.getElementById("rectorCardsView").style.display = "none";
      document.getElementById("rectorNoticeView").style.display = "block";
      const sel = document.getElementById("noticeTargetSelect");
      sel.innerHTML = "";

      if (currentRector.role === "ADMIN" || currentRector.role === "ALL_RECTOR" || currentRector.name === "Nirmalswami" || currentRector.std === "ALL") {
        sel.innerHTML = `<option value="ALL">Entire Hostel (All Students)</option><option value="12">STD 12</option><option value="11">STD 11</option><option value="10">STD 10</option><option value="9">STD 9</option><option value="8">STD 8</option><option value="7">STD 7</option>`;
      } else {
        let stdArr = Array.isArray(currentRector.std) ? currentRector.std : [currentRector.std];
        stdArr.forEach(st => {
          sel.innerHTML += `<option value="${st}">My Wing (STD ${st})</option>`;
        });
      }
      loadRectorNotices();
    }

    function backFromNotice() {
      document.getElementById("rectorNoticeView").style.display = "none";
      document.getElementById("rectorCardsView").style.display = "block";
    }

    function publishNotice() {
      const target = document.getElementById("noticeTargetSelect").value;
      const title = document.getElementById("noticeTitleInput").value.trim();
      const detail = document.getElementById("noticeDetailInput").value.trim();
      const fileInput = document.getElementById("noticeImageInput");

      if (!title || !detail) { alert("Please enter notice title and details!"); return; }

      const notices = JSON.parse(localStorage.getItem("hostel_notices") || "[]");
      const currentRectorId = String(currentRector.id || currentRector.phone || currentRector.name || "");

      function saveNotice(imageData) {
        notices.unshift({
          id: Date.now(),
          title: title,
          detail: detail,
          image: imageData || "",
          target: target,
          rectorName: currentRector.name,
          rectorId: currentRectorId,
          date: new Date().toLocaleDateString("en-US")
        });

        localStorage.setItem("hostel_notices", JSON.stringify(notices));
        alert("Notice published successfully!");
        document.getElementById("noticeTitleInput").value = "";
        document.getElementById("noticeDetailInput").value = "";
        if (fileInput) fileInput.value = "";
        loadRectorNotices();
      }

      if (fileInput && fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = function(e) {
          saveNotice(e.target.result);
        };
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        saveNotice("");
      }
    }

    function loadRectorNotices() {
      const container = document.getElementById("rectorNoticeListContainer");
      const notices = JSON.parse(localStorage.getItem("hostel_notices") || "[]");
      if (notices.length === 0) {
        container.innerHTML = '<p style="color:gray;">No notices published yet.</p>';
        return;
      }

      const activeRectorKey = String(currentRector.id || currentRector.phone || currentRector.name || "");
      let html = "";

      notices.forEach(n => {
        const isAuthor = (n.rectorId && String(n.rectorId) === activeRectorKey) || (!n.rectorId && n.rectorName === currentRector.name);
        const canDelete = isAuthor || (currentRector.role === "ADMIN" || currentRector.name === "Nirmalswami");

        const deleteBtnHtml = canDelete
          ? `<button type="button" onclick="deleteNotice(${n.id})" style="width:auto; padding:4px 8px; font-size:11px; background:#d93025; margin:0;">🗑️ Delete</button>`
          : `<span style="font-size:11px; color:gray; background:#f1f3f4; padding:3px 6px; border-radius:4px;">🔒 Read Only</span>`;

        html += `
          <div class="notice-card">
            <div style="display:flex; justify-content:space-between;">
              <span style="background:#e8f0fe; color:#1a73e8; padding:3px 8px; border-radius:4px; font-weight:bold; font-size:12px;">
                ${n.target === 'ALL' ? 'All Students' : 'STD ' + n.target}
              </span>
              <small style="color:gray;">${n.date}</small>
            </div>
            <h4 style="margin:8px 0 4px 0;">${n.title}</h4>
            <p style="margin:0 0 8px 0; font-size:14px; white-space:pre-line;">${n.detail}</p>
            ${n.image ? `<img src="${n.image}" style="max-width:100%; max-height:220px; border-radius:8px; margin:6px 0;" alt="Notice Image">` : ''}
            <div style="display:flex; justify-content:space-between; align-items:center; margin-top:6px;">
              <small style="color:#1a73e8; font-weight:bold;">By: ${n.rectorName}</small>
              ${deleteBtnHtml}
            </div>
          </div>
        `;
      });
      container.innerHTML = html;
    }

    function deleteNotice(id) {
      let notices = JSON.parse(localStorage.getItem("hostel_notices") || "[]");
      const notice = notices.find(n => Number(n.id) === Number(id));
      if (!notice) return;

      const activeRectorKey = String(currentRector.id || currentRector.phone || currentRector.name || "");
      const isAuthor = (notice.rectorId && String(notice.rectorId) === activeRectorKey) || (!notice.rectorId && notice.rectorName === currentRector.name);
      const canDelete = isAuthor || (currentRector.role === "ADMIN" || currentRector.name === "Nirmalswami");

      if (!canDelete) {
        alert("This notice can only be deleted by " + notice.rectorName + " or Admin!");
        return;
      }

      if (!confirm("Are you sure you want to delete this notice?")) return;
      notices = notices.filter(n => Number(n.id) !== Number(id));
      localStorage.setItem("hostel_notices", JSON.stringify(notices));
      alert("Notice deleted successfully!");
      loadRectorNotices();
    }

    /* RECTOR PROFILE */
    function openRectorProfileView() {
      if (!currentRector) return;
      document.getElementById("rectorCardsView").style.display = "none";
      document.getElementById("rectorProfileView").style.display = "block";
      
      document.getElementById("profRectorName").innerText = currentRector.name || "-";
      document.getElementById("profRectorPhone").innerText = currentRector.phone || currentRector.id || "-";
      document.getElementById("profRectorStd").innerText = currentRector.std === "ALL" ? "All Standards" : "Standard " + (Array.isArray(currentRector.std) ? currentRector.std.join(", ") : currentRector.std);
      document.getElementById("profRectorMed").innerText = (currentRector.medium || "ALL") + " Medium";
      document.getElementById("profRectorRoleDisplay").innerText = (currentRector.role === "ADMIN" || currentRector.name === "Nirmalswami") ? "Chief Admin" : "Hostel Rector";
      document.getElementById("profRectorPhoto").src = getRectorPhoto(currentRector);
    }

    function backFromRectorProfile() {
      document.getElementById("rectorProfileView").style.display = "none";
      document.getElementById("rectorCardsView").style.display = "block";
    }

    /* STUDENT SUB-VIEWS */
    function showStudentSubView(html) {
      document.getElementById("home").style.display = "none";
      const sub = document.getElementById("studentSubPage");
      sub.innerHTML = html;
      sub.style.display = "block";
    }

    function backToHome() {
      document.getElementById("studentSubPage").style.display = "none";
      document.getElementById("home").style.display = "block";
      updateStudentCardAttendanceBadge();
      if (currentStudent) {
        document.getElementById("studentHomePhoto").src = getStudentPhoto(currentStudent);
      }
    }

    function updateStudentCardAttendanceBadge() {
      if (!currentStudent) return;
      const s = currentStudent;
      const savedAll = JSON.parse(localStorage.getItem("hostel_attendance") || "{}");
      let totalSlots = 0, presentSlots = 0;

      for (let d in savedAll) {
        if (savedAll[d]) {
          if (typeof savedAll[d][s.id] === "string") {
            totalSlots++;
            if (savedAll[d][s.id] === "P") presentSlots++;
          } else if (typeof savedAll[d][s.id] === "object") {
            for (let slotKey in savedAll[d][s.id]) {
              totalSlots++;
              if (savedAll[d][s.id][slotKey].status === "P") presentSlots++;
            }
          }
        }
      }

      const badge = document.getElementById("studentCardAttendanceBadge");
      if (badge) {
        const pct = totalSlots === 0 ? 100 : Math.round((presentSlots / totalSlots) * 100);
        badge.innerText = pct + "% Attendance";
        badge.style.color = "#ffffff";
      }
    }

    function studentDetails() {
      if (!currentStudent) return;
      const s = currentStudent;
      const isEng = s.medium === "English" || String(s.class || "").toLowerCase().includes("th");
      const photo = getStudentPhoto(s);
      const fPhone = s.fatherPhone || s.emergencyPhone || "-";

      showStudentSubView(`
        <div style="background: #1a73e8; color: white; padding: 20px; text-align: center; border-radius: 8px;">
          <h2 style="margin: 0;">Student Details</h2>
          <p style="margin: 5px 0 0 0; opacity:0.9;">Dharmjivan Chhatralay</p>
        </div>
        <div style="background: white; padding: 20px; border-radius: 12px; text-align: center; margin-top: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
          
          <div style="position:relative; width:95px; margin:0 auto 10px auto;">
            <img src="${photo}" class="profile-photo" alt="Photo">
            <label for="studentPhotoInput" style="display:inline-block; margin-top:8px; background:#1a73e8; color:white; padding:4px 10px; border-radius:6px; font-size:12px; cursor:pointer;">
              📷 Update
            </label>
            <input type="file" id="studentPhotoInput" accept="image/*" onchange="updateStudentPhoto(this)" style="display:none;">
          </div>

          <h3 style="margin: 10px 0 5px 0;">${s.firstName || ''} ${s.surname || ''}</h3>
          <p style="color:gray; margin:0 0 15px 0;">HR No: ${s.id}</p>

          <div style="text-align:left; background:#f8f9fa; padding:12px; border-radius:8px; font-size:14px; line-height:1.8;">
            <b>Father Name:</b> ${s.fatherName || '-'}<br>
            <b>Father Phone:</b> <a href="tel:${fPhone}" style="color:#1a73e8; text-decoration:none;">📞 ${fPhone}</a><br>
            <b>Standard:</b> STD ${s.stdNumber || s.class} (${isEng ? 'English' : 'Gujarati'})<br>
            <b>Room No:</b> ${s.room || '-'}<br>
            <b>Bed No:</b> ${s.bed || '-'}
          </div>

          <button type="button" onclick="backToHome()" style="background: #1a73e8; color: white; width: 100%; margin-top:15px;">Back</button>
        </div>
      `);
    }

    function viewStudentAttendance() {
      if (!currentStudent) return;
      const s = currentStudent;
      const savedAll = JSON.parse(localStorage.getItem("hostel_attendance") || "{}");
      const dates = Object.keys(savedAll).sort().reverse();

      let totalSlots = 0, presentSlots = 0, absentSlots = 0;
      let slotLogsHtml = "";

      dates.forEach(d => {
        if (savedAll[d] && savedAll[d][s.id]) {
          const rec = savedAll[d][s.id];
          let rows = "";

          if (typeof rec === "string") {
            totalSlots++;
            if (rec === "P") presentSlots++; else absentSlots++;
            const isP = (rec === "P");
            rows += `
              <div class="slot-row">
                <span>General Attendance</span>
                <b style="color:${isP ? '#0f9d58' : '#d93025'};">${isP ? '✅ Present (P)' : '❌ Absent (A)'}</b>
              </div>
            `;
          } else if (typeof rec === "object") {
            for (let slotKey in rec) {
              totalSlots++;
              const isP = (rec[slotKey].status === "P");
              if (isP) presentSlots++; else absentSlots++;
              const reasonText = rec[slotKey].reason ? `<br><small style="color:#d93025;">કારણ: <b>${rec[slotKey].reason}</b></small>` : '';
              rows += `
                <div class="slot-row">
                  <div>
                    <b>${slotKey}</b><br>
                    <small style="color:gray;">Time: ${rec[slotKey].time || '-'} | By: ${rec[slotKey].rector || 'Rector'}</small>
                    ${reasonText}
                  </div>
                  <span style="font-weight:bold; font-size:12px; padding:3px 8px; border-radius:4px; background:${isP ? '#e6f4ea' : '#fce8e6'}; color:${isP ? '#137333' : '#d93025'};">
                    ${isP ? 'Present' : 'Absent'}
                  </span>
                </div>
              `;
            }
          }

          if (rows) {
            slotLogsHtml += `
              <div style="background:white; border-left:4px solid #1a73e8; padding:10px; margin-bottom:10px; border-radius:6px; box-shadow:0 1px 4px rgba(0,0,0,0.05); text-align:left;">
                <b style="color:#1a73e8; display:block; margin-bottom:6px;">📅 Date: ${d}</b>
                ${rows}
              </div>
            `;
          }
        }
      });

      const percentage = totalSlots > 0 ? Math.round((presentSlots / totalSlots) * 100) : 100;

      showStudentSubView(`
        <div style="background: #1a73e8; color: white; padding: 20px; text-align: center; border-radius: 8px;">
          <h2 style="margin: 0;">Attendance Report</h2>
          <p style="margin: 5px 0 0 0; opacity:0.9;">Slot-wise Record</p>
        </div>
        <div style="background: white; padding: 20px; border-radius: 12px; text-align: center; margin-top: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
          <div style="font-size: 50px;">📊</div>
          <h3>${s.firstName || ''} ${s.surname || ''}</h3>
          <p style="font-size: 26px; color: ${percentage >= 75 ? '#0f9d58' : '#d93025'}; font-weight: bold; margin: 10px 0;">${percentage}% Overall</p>
          <hr style="border: 0; border-top: 1px solid #eee; margin: 15px 0;">
          <div style="display:flex; justify-content:space-around; margin-bottom:15px; font-size:14px;">
            <span>Total Slots: <b>${totalSlots}</b></span>
            <span style="color:#0f9d58;">Present: <b>${presentSlots}</b></span>
            <span style="color:#d93025;">Absent: <b>${absentSlots}</b></span>
          </div>

          <h4 style="text-align:left; color:#333; margin:15px 0 10px 0;">Slot-wise Log:</h4>
          ${slotLogsHtml || '<p style="color:gray; padding:15px;">No slot attendance recorded yet.</p>'}

          <button type="button" onclick="backToHome()" style="background: #1a73e8; color: white; width: 100%; margin-top: 15px;">Back</button>
        </div>
      `);
    }

    function viewStudentComplaints() {
      activeStudentRecordTab = "SMARTWORK";
      renderStudentRecordsView();
    }

    function switchStudentRecordTab(tab) {
      activeStudentRecordTab = tab;
      renderStudentRecordsView();
    }

    function renderStudentRecordsView() {
      if (!currentStudent) return;
      const s = currentStudent;
      const allComplaints = JSON.parse(localStorage.getItem("hostel_complaints") || "[]");
      const myRecords = allComplaints.filter(c => String(c.studentId) === String(s.id));

      let contentHtml = "";

      if (activeStudentRecordTab === "SMARTWORK") {
        const smartRecords = myRecords.filter(c => c.category === "SMARTWORK");
        if (smartRecords.length === 0) {
          contentHtml = `<p style="color:gray; padding:20px; text-align:center;">No smart work entries recorded yet.</p>`;
        } else {
          smartRecords.forEach(c => {
            contentHtml += `
              <div class="smartwork-card">
                <div style="display:flex; justify-content:space-between;">
                  <span style="background: #e6f4ea; color: #137333; padding: 2px 8px; border-radius: 4px; font-weight: bold; font-size: 11px;">${c.type}</span>
                  <small style="color: gray;">${c.date}</small>
                </div>
                <p style="margin: 8px 0; font-size: 13px; color:#333;">${c.detail}</p>
                ${c.photo ? `<img src="${c.photo}" style="max-width:100%; max-height:200px; border-radius:6px; margin:6px 0;" alt="Smart Work Photo">` : ''}
                <small style="color: #666; display:block; margin-top:4px;">By: <b>${c.rectorName}</b></small>
              </div>
            `;
          });
        }
      } else {
        const compRecords = myRecords.filter(c => c.category !== "SMARTWORK");
        if (compRecords.length === 0) {
          contentHtml = `<div style="background: #e6f4ea; color: #137333; padding: 15px; border-radius: 6px; font-size:13px; font-weight:bold; text-align:center;">✅ Clean Record! No complaints recorded.</div>`;
        } else {
          compRecords.forEach(c => {
            contentHtml += `
              <div class="complaint-card">
                <div style="display:flex; justify-content:space-between;">
                  <span style="background: #fce8e6; color: #d93025; padding: 2px 8px; border-radius: 4px; font-weight: bold; font-size: 11px;">${c.type}</span>
                  <small style="color: gray;">${c.date}</small>
                </div>
                <p style="margin: 8px 0; font-size: 13px; color:#333;">${c.detail}</p>
                ${c.photo ? `<img src="${c.photo}" style="max-width:100%; max-height:200px; border-radius:6px; margin:6px 0;" alt="Complaint Photo">` : ''}
                <small style="color: #666; display:block; margin-top:4px;">By: <b>${c.rectorName}</b></small>
              </div>
            `;
          });
        }
      }

      showStudentSubView(`
        <div style="background: #1a73e8; color: white; padding: 20px; text-align: center; border-radius: 8px;">
          <h2 style="margin: 0;">Smart Work & Complaints</h2>
          <p style="margin: 5px 0 0 0; opacity:0.9;">Positive & Negative History</p>
        </div>
        <div style="background: white; padding: 20px; border-radius: 12px; margin-top: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
          <h3>${s.firstName || ''} ${s.surname || ''}</h3>

          <div class="tab-btn-group" style="margin-top:15px;">
            <div class="tab-btn ${activeStudentRecordTab === 'SMARTWORK' ? 'tab-active-smart' : ''}" onclick="switchStudentRecordTab('SMARTWORK')">
              🌟 Smart Work
            </div>
            <div class="tab-btn ${activeStudentRecordTab === 'COMPLAINT' ? 'tab-active-complaint' : ''}" onclick="switchStudentRecordTab('COMPLAINT')">
              📝 Complaints
            </div>
          </div>

          <div style="margin-top:15px; text-align:left;">
            ${contentHtml}
          </div>

          <button type="button" onclick="backToHome()" style="background: #1a73e8; color: white; width: 100%; margin-top: 20px;">Back</button>
        </div>
      `);
    }

    function viewStudentNotices() {
      if (!currentStudent) return;
      const s = currentStudent;
      const stdNum = String(s.stdNumber || s.class || "").replace(/\D/g, "");
      const allNotices = JSON.parse(localStorage.getItem("hostel_notices") || "[]");
      const myNotices = allNotices.filter(n => !n.target || n.target === "ALL" || String(n.target) === String(stdNum));

      let noticesListHtml = "";
      if (myNotices.length === 0) {
        noticesListHtml = `<div style="background: #f1f3f4; color: #5f6368; padding: 20px; border-radius: 8px; margin: 20px 0; text-align: center;"><div style="font-size: 40px;">📭</div><b>No notices available!</b></div>`;
      } else {
        myNotices.forEach(n => {
          noticesListHtml += `
            <div class="notice-card">
              <div style="display:flex; justify-content:space-between;">
                <span style="background: #e8f0fe; color: #1a73e8; padding: 2px 8px; border-radius: 4px; font-weight: bold; font-size: 11px;">${n.target === 'ALL' ? 'Hostel Wide' : 'STD ' + n.target}</span>
                <small style="color: gray;">${n.date || ''}</small>
              </div>
              <h4 style="margin: 8px 0 4px 0; color: #1a73e8;">${n.title || ''}</h4>
              <p style="margin: 0 0 8px 0; font-size: 14px; white-space: pre-line;">${n.detail || ''}</p>
              ${n.image ? `<img src="${n.image}" style="max-width:100%; max-height:220px; border-radius:8px; margin:6px 0;" alt="Notice">` : ''}
              <small style="color: #5f6368; display:block; margin-top:4px;">By: <b>${n.rectorName || 'Rector'}</b></small>
            </div>
          `;
        });
      }

      showStudentSubView(`
        <div style="background: #1a73e8; color: white; padding: 20px; text-align: center; border-radius: 8px;">
          <h2 style="margin: 0;">Notice Board</h2>
        </div>
        <div style="background: white; padding: 20px; border-radius: 12px; margin-top: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
          ${noticesListHtml}
          <button type="button" onclick="backToHome()" style="background: #1a73e8; color: white; width: 100%; margin-top: 15px;">Back</button>
        </div>
      `);
    }

    function viewStudentNightCheck() {
      if (!currentStudent) return;
      const s = currentStudent;
      const allChecks = JSON.parse(localStorage.getItem("hostel_night_checks") || "{}");
      const dates = Object.keys(allChecks).sort().reverse();
      let recordsHtml = "";
      let foundAny = false;

      dates.forEach(d => {
        const roomData = (allChecks[d] && s.room && allChecks[d][s.room]) ? allChecks[d][s.room] : null;
        if (roomData && roomData.students && roomData.students[s.id]) {
          foundAny = true;
          let st = "PRESENT";
          let rs = "";
          if (typeof roomData.students[s.id] === "string") {
            st = roomData.students[s.id];
          } else if (typeof roomData.students[s.id] === "object") {
            st = roomData.students[s.id].status || "PRESENT";
            rs = roomData.students[s.id].reason || "";
          }

          const isPresent = (st === "PRESENT");
          recordsHtml += `
            <div style="background: white; border-left: 5px solid ${isPresent ? '#0f9d58' : '#d93025'}; padding: 12px; margin-bottom: 12px; border-radius: 6px; box-shadow: 0 2px 5px rgba(0,0,0,0.06); text-align: left;">
              <div style="display: flex; justify-content: space-between;">
                <b>📅 Date: ${d}</b>
                <span style="background: ${isPresent ? '#e6f4ea' : '#fce8e6'}; color: ${isPresent ? '#137333' : '#d93025'}; padding: 3px 8px; border-radius: 4px; font-weight: bold; font-size: 12px;">${isPresent ? '✅ Present' : '❌ Absent'}</span>
              </div>
              <p style="margin: 6px 0; font-size: 13px; color: #555;">Check Time: <b>${roomData.time || '-'}</b> | Room: <b>${s.room || '-'}</b></p>
              ${(!isPresent && rs) ? `<p style="margin: 4px 0 0 0; font-size: 12px; color: #d93025; background: #fff3f2; padding: 4px 6px; border-radius: 4px;"><b>ગેરહાજર કારણ:</b> ${rs}</p>` : ''}
              ${roomData.remark ? `<p style="margin: 4px 0 0 0; font-size: 12px; color: #555;"><b>રૂમ રીમાર્ક:</b> ${roomData.remark}</p>` : ''}
              <small style="color: #1a73e8; display: block; margin-top: 4px;">Checked By: <b>${roomData.checkedBy || 'Rector'}</b></small>
            </div>
          `;
        }
      });

      if (!foundAny) {
        recordsHtml = `<div style="background: #f1f3f4; color: #5f6368; padding: 25px; border-radius: 8px; margin: 20px 0; text-align: center;"><div style="font-size: 40px;">🌙</div><b>No night check record found yet!</b></div>`;
      }

      showStudentSubView(`
        <div style="background: #1a73e8; color: white; padding: 20px; text-align: center; border-radius: 8px;">
          <h2 style="margin: 0;">Night Check Status</h2>
        </div>
        <div style="background: white; padding: 15px; border-radius: 12px; margin-top: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
          <h3>${s.firstName || ''} ${s.surname || ''}</h3>
          <p style="color: gray; font-size: 13px; margin: 0 0 10px 0;">Room No: ${s.room || '-'} | Bed No: ${s.bed || '-'}</p>
          <hr style="border: 0; border-top: 1px solid #eee; margin: 10px 0;">
          ${recordsHtml}
          <button type="button" onclick="backToHome()" style="background: #1a73e8; color: white; width: 100%; margin-top: 15px;">Back</button>
        </div>
      `);
    }

    /* HOSTEL OFFICE CONTACT */
    function isOfficeCallTimeAllowed() {
      const now = new Date();
      const cur = now.getHours() * 60 + now.getMinutes();
      if (cur >= 540 && cur <= 720) return true;
      if (cur >= 960 && cur <= 1140) return true;
      if (cur >= 1230 && cur <= 1350) return true;
      return false;
    }

    function viewHostelContacts() {
      const canCall = isOfficeCallTimeAllowed();

      showStudentSubView(`
        <div style="background: #1a73e8; color: white; padding: 20px; text-align: center; border-radius: 8px;">
          <h2 style="margin: 0;">Hostel Contacts</h2>
          <p style="margin: 5px 0 0 0; opacity:0.9;">Dharmjivan Chhatralay</p>
        </div>
        <div style="background: white; padding: 20px; border-radius: 12px; margin-top: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
          
          <div style="text-align:center; padding: 10px 0 15px 0;">
            <div style="font-size: 45px; margin-bottom: 5px;">🏢</div>
            <h3 style="margin: 0; color: #1a73e8; font-size: 22px;">Hostel Office</h3>
            <p style="color: gray; margin: 4px 0 10px 0; font-size: 13px;">Official inquiries and assistance</p>
            <b style="font-size: 22px; color: #333; display:block; margin: 8px 0; letter-spacing: 1px;">📞 909421000</b>
          </div>

          <div style="background: #f8f9fa; border: 1px solid #e0e0e0; padding: 12px; border-radius: 8px; font-size: 13px; line-height: 1.6; margin-bottom: 18px; text-align: left;">
            <b style="color: #1a73e8;">🕒 Calling Hours (ફોન કરવાનો સમય):</b><br>
            • Morning: <b>9:00 AM to 12:00 PM</b><br>
            • Afternoon: <b>4:00 PM to 7:00 PM</b><br>
            • Night: <b>8:30 PM to 10:30 PM</b>
          </div>

          ${canCall ? `
            <a href="tel:9099421000" style="display:block; text-align:center; background:#0f9d58; color:white; padding:13px; border-radius:8px; text-decoration:none; font-weight:bold; font-size:16px; box-shadow:0 3px 8px rgba(15,157,88,0.3);">
              📞 Call Office Now
            </a>
          ` : `
            <button type="button" disabled style="background:#9e9e9e; color:white; width:100%; padding:13px; border-radius:8px; border:none; font-size:14px; font-weight:bold;">
              🔒 Calling Closed (Available Only During Office Hours)
            </button>
          `}

          <button type="button" onclick="backToHome()" style="background: #1a73e8; color: white; width: 100%; margin-top: 15px;">Back</button>
        </div>
      `);
    }
  </script>
<script>
window.students = [

  {id:"236101",surname:"PATEL",firstName:"PRINCE",fatherName:"SATISHBHAI",class:"10th",room:"6",bed:"113",password: PRI101}

  ]

// Medium olkhava ane Password banavva nu saachu logic:
window.students = window.students.map(function(student) {
  var rawClass = String(student.class).trim();
  var isEnglish = rawClass.toLowerCase().includes("th");
  var stdNum = rawClass.replace(/[^0-9]/g, ""); // Khali ankdo (7, 8, 9, 10)
  
  var fName = (student.firstName || "").replace(/[^a-zA-Z]/g, "");
  var passPrefix = (fName.length >= 3) ? fName.slice(0, 3).toUpperCase() : fName.toUpperCase().padEnd(3, 'X');
  var passSuffix = String(student.id).slice(-3);
  
  return {
    ...student,
    stdNumber: stdNum, // Filter karva mate ankdo
    medium: isEnglish ? "English" : "Gujarati", // Medium olkhai jase
    displayClass: isEnglish ? (stdNum + "th (Eng)") : (stdNum + " (Guj)"), // Table ma dekhava mate
    password: passPrefix + passSuffix
  };
});

// ==========================================
  // મુખ્ય એડમિન: recoter
  // ==========================================
  {
    id: "NIRMALSWAMI"
    name: "Nirmalswami"
    password: "Admin 86251"
    role: "ADMIN"
    std: "ALL"
    medium: "ALL"
    wing: "ALL"
  }

// Rector Data
window.rectors = [
  
  {
    id: "DARSHANBHAI",
    phone: "8320056739",
    name: "Darshanbhai",
    password: "rupapara739",
    std: "ALL",
    medium: "ALL"
  },
  {
    id: "HARIKRUSHNABHAI",
    phone: "8160404575",
    name: "Harikrushnabhai",
    password: "sheldia575",
    std: ["7","8"],
    medium: "Gujarati"
  },
  {
    id: "DHAIRYBHAI",
    phone: "9974159968",
    name: "Dhairybhai",
    password: "patel968",
    std: ["7","8"],
    medium: "ALL"
  },
  {
    id: "YASHBHAI",
    phone: "9106924414",
    name: "Yashbhai",
    password: "danger414",
    std: ["7","8"],
    medium: "Gujarati"
  },
  {
    id: "RAMESHSIR",
    phone: "9714216930",
    name: "Rameshsir",
    password: "16930",
    std: "9",
    medium: "Gujarati"
  },
  {
    id: "ASHISHBHAI",
    phone: "9624061598",
    name: "Ashishbhai",
    password: "kalsariya598",
    std: "9",
    medium: "English"
  },
  {
    id: "VIVEKBHAI",
    phone: "9773178071",
    name: "Vivekbhai",
    password: "narola071",
    std: "10",
    medium: "ALL"
  },
  {
    id: "DHARMIKBHAI",
    phone: "9909187068",
    name: "Dharmikbhai",
    password: "jagani068",
    std: "ALL",
    medium: "ALL"
  },
  {
    id: "GURJISIR",
    phone: "9726978299",
    name: "Gurjisir",
    password: "vasava299",
    std: ["11","12"],
    medium: "ALL"
  },
  {
    id: "TANMAYBHAI",
    phone: "6351223418",
    name: "Tanmaybhai",
    password: "patel418",
    std: ["7","8"],
    medium: "English"
  },
  {
    id: "UDAYBHAI"
    phone: ""
    name: "Udaybhai"
    password: "Kanani046"
    std: ["9"]
    medium: "Gujarati"
 }
];
</script>
</body>
</html>
