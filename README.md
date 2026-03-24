html
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>منصة المدرسة</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
  <script src="script.js"></script>
</head>
<body>
  <h1>منصة المدرسة</h1>

  <!-- تسجيل الدخول -->
  <section id="login">
    <input type="text" id="code" placeholder="ادخل الرمز">
    <button onclick="login()">دخول</button>
  </section>

  <!-- رسالة ترحيب -->
  <section id="welcome" style="display:none;">
    <h2 id="welcomeMessage"></h2>
  </section>

  <!-- الاستطلاع -->
  <section id="poll" style="display:none;">
    <h2 id="pollQuestion">هل تحبين مادة الرياضيات؟</h2>
    <button onclick="vote('yes')">نعم</button>
    <button onclick="vote('no')">لا</button>
    <p id="pollResult"></p>
    <div id="pollEdit" style="display:none;">
      <input type="text" id="newQuestion" placeholder="اكتبي سؤال جديد">
      <button onclick="updatePoll()">تحديث الاستطلاع</button>
    </div>
  </section>

  <!-- الجدول -->
  <section id="schedule" style="display:none;">
    <h2>الجدول الأسبوعي</h2>
    <img id="scheduleImage" src="" style="max-width:100%; display:none;">
    <div id="scheduleUpload" style="display:none;">
      <input type="file" id="uploadInput" accept="image/*">
      <button onclick="uploadSchedule()">رفع الجدول</button>
    </div>
  </section>

  <!-- المنتدى -->
  <section id="forum" style="display:none;">
    <h2>منتدى المدرسة</h2>
    <textarea id="comment" placeholder="اكتبي تعليقك هنا"></textarea>
    <button onclick="postComment()">إرسال</button>
    <div id="comments"></div>
  </section>

  <!-- الإعلانات -->
  <section id="announcements" style="display:none;">
    <h2>إعلانات المدرسة</h2>
    <div id="announcementList"></div>
    <div id="announcementEdit" style="display:none;">
      <textarea id="newAnnouncement" placeholder="اكتبي الإعلان هنا"></textarea>
      <button onclick="addAnnouncement()">إضافة إعلان</button>
    </div>
  </section>

  <!-- الملفات -->
  <section id="files" style="display:none;">
    <h2>ملفات المدرسة</h2>
    <div id="fileList"></div>
    <div id="fileUpload" style="display:none;">
      <input type="file" id="pdfInput" accept="application/pdf">
      <button onclick="uploadPDF()">رفع ملف PDF</button>
    </div>
  </section>

  <!-- الدرجات -->
  <section id="grades" style="display:none;">
    <h2>الدرجات</h2>
    <div id="gradesContainer"></div>
    <div id="gradesUpload" style="display:none;">
      <input type="file" id="gradesInput" accept="image/*">
      <input type="text" id="gradesClass" placeholder="اكتبي اسم الشعبة">
      <button onclick="uploadGrades()">رفع صورة الدرجات</button>
    </div>
  </section>

  <!-- لوحة تحكم المالكة -->
  <section id="ownerPanel" style="display:none;">
    <h2>لوحة تحكم المالكة</h2>
    <button onclick="manageCodes()">إدارة الرموز</button>
    <button onclick="viewStats()">عرض الإحصائيات</button>
    <button onclick="pausePlatform()">إيقاف المنصة مؤقتًا</button>
    <button onclick="viewLogs()">عرض سجل النشاطات</button>
    <button onclick="downloadLogs()">تنزيل سجل النشاطات كملف PDF</button>
    <div id="activityLog"></div>
  </section>
</body>
</html>
https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.jsjavascript
// تسجيل الدخول
function login() {
  const code = document.getElementById("code").value;

  // رمز المعلمات
  if (code === "TEACHER-MANSOUR") {
    alert("مرحباً بالمعلمة!");
    showSections();
  }

  // الصف الأول
  else if (code === "XK47" || code === "BM93" || code === "QP28" || code === "WN56" || code === "TR81") {
    alert("مرحباً بطالبات الأول!");
    showSections();
  }

  // الصف الثاني
  else if (code === "AZ34" || code === "RL87" || code === "DY62" || code === "FG15") {
    alert("مرحباً بطالبات الثاني!");
    showSections();
  }

  // الصف الثالث
  else if (code === "JT59" || code === "NX24" || code === "GW73" || code === "CF96") {
    alert("مرحباً بطالبات الثالث!");
    showSections();
  }

  // الصف الرابع
  else if (code === "KV38" || code === "LQ85" || code === "HB67" || code === "ZP42") {
    alert("مرحباً بطالبات الرابع!");
    showSections();
  }

  // الصف الخامس
  else if (code === "YM71" || code === "SK29" || code === "UN54" || code === "FT86") {
    alert("مرحباً بطالبات الخامس!");
    showSections();
  }

  // الصف السادس
  else if (code === "EW43" || code === "PR69" || code === "VZ37" || code === "MJ81") {
    alert("مرحباً بطالبات السادس!");
    showSections();
  }

  // إذا الرمز غير صحيح
  else {
    alert("رمز غير صحيح!");
  }
}

