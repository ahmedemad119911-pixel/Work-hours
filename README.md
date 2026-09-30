 ## Work-hours-[index.html](https://github.com/user-attachments/files/32834818/index.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>ساعات الشغل</title>
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="ساعات الشغل">
<link rel="apple-touch-icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 180 180'%3E%3Crect width='180' height='180' rx='36' fill='%23182922'/%3E%3Ccircle cx='90' cy='96' r='58' fill='none' stroke='%23C99A4A' stroke-width='9'/%3E%3Cline x1='90' y1='96' x2='90' y2='58' stroke='%23F1EDE4' stroke-width='8' stroke-linecap='round'/%3E%3Cline x1='90' y1='96' x2='118' y2='104' stroke='%23F1EDE4' stroke-width='8' stroke-linecap='round'/%3E%3Crect x='72' y='22' width='36' height='16' rx='6' fill='%23C99A4A'/%3E%3C/svg%3E">

<style>
  :root{
    --bg:#EDE7D8;
    --surface:#F9F5EA;
    --ink:#20291F;
    --ink-soft:#6B6353;
    --line:#DCD3BC;
    --accent:#9C7331;
    --accent-ink:#F9F5EA;
    --regular:#2F6F4E;
    --regular-soft:#DEE9DF;
    --overtime:#B0591A;
    --overtime-soft:#F1DFC6;
    --danger:#A23B2E;
    padding-top:env(safe-area-inset-top,0px);
    padding-bottom:env(safe-area-inset-bottom,0px);
    box-sizing:border-box;
  }
  @media (prefers-color-scheme:dark){
    :root:not([data-theme="light"]){
      --bg:#141E19; --surface:#1B2620; --ink:#EFE9DA; --ink-soft:#9BA69A; --line:#2B372F;
      --accent:#D3A455; --accent-ink:#141E19; --regular:#5CAE81; --regular-soft:#213A2C;
      --overtime:#E08C43; --overtime-soft:#3B2C1B; --danger:#E07360;
    }
  }
  :root[data-theme="dark"]{
    --bg:#141E19; --surface:#1B2620; --ink:#EFE9DA; --ink-soft:#9BA69A; --line:#2B372F;
    --accent:#D3A455; --accent-ink:#141E19; --regular:#5CAE81; --regular-soft:#213A2C;
    --overtime:#E08C43; --overtime-soft:#3B2C1B; --danger:#E07360;
  }
  html,body{height:100%;}
  *{box-sizing:border-box;}
  body{
    margin:0; background:var(--bg); color:var(--ink);
    font-family:system-ui,-apple-system,'Segoe UI','Geeza Pro',sans-serif;
    min-height:100%; -webkit-font-smoothing:antialiased; overflow-x:hidden;
  }
  html[dir="ltr"] body{ font-family:system-ui,-apple-system,'Segoe UI',sans-serif; }
  html[dir="ltr"] .mono, html[dir="ltr"] .clock, html[dir="ltr"] .ampm { font-family:ui-monospace,'SF Mono',Menlo,Consolas,monospace; }
  .mono{font-family:ui-monospace,'SF Mono',Menlo,Consolas,monospace; font-variant-numeric:tabular-nums;}
  .tab-page{display:none; padding:18px 18px 100px;}
  .tab-page.active{display:block;}
  .app{max-width:480px; margin:0 auto; min-height:100%; position:relative;}

  .datebar{text-align:center; padding-top:14px; color:var(--ink-soft); font-size:14px;}
  .hero{ text-align:center; padding:22px 0 26px; border-bottom:1px solid var(--line); margin-bottom:18px; }
  .hero .clock{ font-size:56px; font-weight:600; letter-spacing:1px; line-height:1; }
  .hero .ampm{font-size:20px; color:var(--ink-soft); margin-inline-start:6px;}
  .status-line{margin-top:10px; font-size:15px; color:var(--ink-soft); min-height:20px;}
  .status-line.working{color:var(--regular);}
  .status-line.overtime{color:var(--overtime);}

  .punch-btn{
    width:100%; padding:20px; border:none; border-radius:10px;
    font-size:18px; font-weight:800; background:var(--regular); color:#fff;
    cursor:pointer; position:relative; overflow:hidden;
    transition:transform .12s ease, background .3s ease;
    font-family:inherit;
  }
  .punch-btn.out{background:var(--ink);}
  .punch-btn.overtime{background:var(--overtime);}
  .punch-btn:active{transform:scale(.97);}
  .stamp-mark{
    position:absolute; inset:0; display:flex; align-items:center; justify-content:center;
    font-size:14px; font-weight:800; letter-spacing:1px; background:rgba(255,255,255,.18);
    opacity:0; pointer-events:none;
  }
  @keyframes stampFade{ 0%{opacity:1; transform:scale(1.3) rotate(-8deg);} 100%{opacity:0; transform:scale(1) rotate(-8deg);} }
  .stamp-mark.show{animation:stampFade .55s ease-out forwards;}

  .banner{
    margin-top:16px; padding:12px 14px; background:var(--overtime-soft); border-radius:8px;
    font-size:14px; color:var(--overtime); display:none;
  }
  .banner.show{display:block;}
  .banner button{
    display:block; margin-top:8px; background:none; border:1px solid var(--overtime); color:var(--overtime);
    padding:6px 12px; border-radius:6px; font-weight:700; font-size:13px; font-family:inherit;
  }

  .section-title{
    font-size:13px; font-weight:700; color:var(--ink-soft);
    padding-bottom:8px; margin-bottom:12px; border-bottom:1px solid var(--line);
  }

  .today-card{margin-top:20px;}
  .today-row{display:flex; justify-content:space-between; padding:8px 0; font-size:15px;}
  .today-row .val{font-weight:600;}
  .val.regular{color:var(--regular);}
  .val.overtime{color:var(--overtime);}

  .month-block{margin-bottom:26px;}
  .month-header{ display:flex; justify-content:space-between; align-items:baseline; padding-bottom:8px; margin-bottom:6px; border-bottom:1px solid var(--line); }
  .month-header .name{font-size:16px; font-weight:800;}
  .month-header .sum{font-size:13px; color:var(--ink-soft);}
  .day-row{ display:flex; justify-content:space-between; align-items:center; padding:12px 0; border-bottom:1px solid var(--line); cursor:pointer; }
  .day-row .left .d{font-size:15px; font-weight:500;}
  .day-row .left .t{font-size:13px; color:var(--ink-soft); margin-top:2px;}
  .day-row .right{text-align:end; font-size:14px;}
  .day-row .right .r{color:var(--regular);}
  .day-row .right .o{color:var(--overtime); margin-inline-start:8px;}
  .empty{text-align:center; color:var(--ink-soft); padding:40px 10px; font-size:14px; line-height:1.9;}

  .fab{
    position:fixed; inset-inline-start:20px; bottom:calc(84px + env(safe-area-inset-bottom,0px));
    width:52px; height:52px; border-radius:50%; background:var(--accent); color:var(--accent-ink);
    border:none; font-size:26px; box-shadow:0 3px 10px rgba(0,0,0,.2); max-width:480px;
  }

  .field{margin-bottom:18px;}
  .field label{display:block; font-size:14px; color:var(--ink-soft); margin-bottom:6px;}
  .field input{
    width:100%; padding:12px 14px; border-radius:8px; border:1px solid var(--line);
    background:var(--surface); color:var(--ink); font-size:16px; font-family:inherit;
  }
  .field .hint{font-size:12px; color:var(--ink-soft); margin-top:5px;}
  .danger-btn{
    width:100%; padding:14px; border-radius:8px; border:1px solid var(--danger);
    background:none; color:var(--danger); font-weight:700; font-size:15px; margin-top:10px; font-family:inherit;
  }

  .lang-toggle{display:flex; border:1px solid var(--line); border-radius:8px; overflow:hidden;}
  .lang-toggle button{
    flex:1; padding:10px; border:none; background:var(--surface); color:var(--ink-soft);
    font-size:14px; font-weight:700; font-family:inherit;
  }
  .lang-toggle button.active{background:var(--accent); color:var(--accent-ink);}

  .chip-row{display:flex; flex-wrap:wrap; gap:8px;}
  .chip{padding:8px 14px; border-radius:20px; border:1px solid var(--line); background:var(--surface);
    color:var(--ink-soft); font-size:13px; font-weight:600; font-family:inherit;}
  .chip.active{background:var(--accent); color:var(--accent-ink); border-color:var(--accent);}

  .field-header{display:flex; justify-content:space-between; align-items:center; margin-bottom:8px;}
  .field-header label{margin:0;}
  .small-add{border:none; background:var(--accent); color:var(--accent-ink); width:28px; height:28px;
    border-radius:50%; font-size:18px; line-height:1; flex-shrink:0;}
  .holiday-row{display:flex; justify-content:space-between; align-items:center; padding:10px 0;
    border-bottom:1px solid var(--line); font-size:14px; cursor:pointer;}
  .holiday-row .hd{color:var(--ink-soft); font-size:13px;}
  .empty-mini{color:var(--ink-soft); font-size:13px; padding:8px 0;}

  .stat-grid{display:grid; grid-template-columns:1fr 1fr; gap:0 12px; margin-bottom:14px;}
  .stat-cell{display:flex; justify-content:space-between; padding:6px 0; border-bottom:1px solid var(--line); font-size:13px;}
  .stat-cell .v{font-weight:700;}
  .stat-cell .v.o{color:var(--overtime);}
  .stat-cell .v.a{color:var(--danger);}
  .sub-heading{font-size:12px; font-weight:700; color:var(--ink-soft); margin:16px 0 4px;}
  textarea.backup-area{width:100%; font-family:ui-monospace,'SF Mono',Menlo,Consolas,monospace; font-size:12px; padding:10px; border-radius:8px; border:1px solid var(--line); background:var(--surface); color:var(--ink); resize:vertical;}

  .nav{
    position:fixed; bottom:0; left:0; right:0; background:var(--surface); border-top:1px solid var(--line);
    padding-bottom:env(safe-area-inset-bottom,0px); display:flex; max-width:480px; margin:0 auto;
  }
  .nav button{
    flex:1; background:none; border:none; padding:12px 4px 10px;
    display:flex; flex-direction:column; align-items:center; gap:4px;
    color:var(--ink-soft); font-size:12px; font-weight:600; font-family:inherit;
  }
  .nav button.active{color:var(--ink);}
  .nav svg{width:22px; height:22px;}

  .sheet-overlay{
    position:fixed; inset:0; background:rgba(0,0,0,.4);
    display:none; align-items:flex-end; justify-content:center; z-index:50;
  }
  .sheet-overlay.show{display:flex;}
  .sheet{
    background:var(--surface); width:100%; max-width:480px; border-radius:16px 16px 0 0;
    padding:20px 20px calc(24px + env(safe-area-inset-bottom,0px)); transform:translateY(100%); transition:transform .25s ease;
  }
  .sheet-overlay.show .sheet{transform:translateY(0);}
  .sheet h3{margin:0 0 16px; font-size:17px;}
  .sheet-actions{display:flex; gap:10px; margin-top:6px;}
  .btn{flex:1; padding:13px; border-radius:8px; border:none; font-weight:700; font-size:15px; font-family:inherit;}
  .btn.save{background:var(--regular); color:#fff;}
  .btn.cancel{background:var(--line); color:var(--ink);}
  .btn.delete{background:none; color:var(--danger); border:1px solid var(--danger);}
</style>
</head>
<body>
<div class="app">

  <div class="tab-page active" id="tab-home">
    <div class="datebar" id="todayDate">—</div>
    <div class="hero">
      <div class="clock mono" id="liveClock">00:00:00</div>
      <div class="status-line" id="statusLine">—</div>
    </div>

    <button class="punch-btn" id="punchBtn"><span id="punchLabel">—</span><span class="stamp-mark" id="stampMark"></span></button>

    <div class="banner" id="staleBanner">
      <span id="staleMsg">—</span>
      <button id="fixStaleBtn"><span id="staleBtnLabel">—</span></button>
    </div>

    <div class="today-card" id="todayCard" style="display:none;">
      <div class="section-title" id="todaySectionTitle">—</div>
      <div class="today-row"><span id="lblIn">—</span><span class="val mono" id="todayIn">—</span></div>
      <div class="today-row"><span id="lblRegular">—</span><span class="val regular mono" id="todayRegular">—</span></div>
      <div class="today-row"><span id="lblOvertime">—</span><span class="val overtime mono" id="todayOvertime">—</span></div>
      <div class="today-row" id="todayPayRow" style="display:none;"><span id="lblOvertimeValue">—</span><span class="val overtime mono" id="todayPay">—</span></div>
    </div>
  </div>

  <div class="tab-page" id="tab-history">
    <div class="section-title" id="historySectionTitle">—</div>
    <div id="historyList"></div>
  </div>
  <button class="fab" id="addEntryFab" style="display:none;">+</button>

  <div class="tab-page" id="tab-settings">
    <div class="section-title" id="settingsSectionTitle">—</div>
    <div class="field">
      <label id="lblLanguage">—</label>
      <div class="lang-toggle">
        <button id="langArBtn">العربية</button>
        <button id="langEnBtn">English</button>
      </div>
    </div>
    <div class="field">
      <label id="lblRestDays">—</label>
      <div class="chip-row" id="restDayChips"></div>
    </div>
    <div class="field">
      <div class="field-header">
        <label id="lblHolidays">—</label>
        <button class="small-add" id="addHolidayBtn">+</button>
      </div>
      <div id="holidayList"></div>
    </div>
    <div class="field">
      <label id="lblStandardHours">—</label>
      <input type="number" id="setStandardHours" step="0.5" min="1" max="16">
    </div>
    <div class="field">
      <label id="lblHourlyRate">—</label>
      <input type="number" id="setHourlyRate" step="0.5" min="0">
    </div>
    <div class="field">
      <label id="lblMultiplier">—</label>
      <input type="number" id="setMultiplier" step="0.1" min="1">
      <div class="hint" id="hintMultiplier">—</div>
    </div>
    <div class="field">
      <label id="lblCurrency">—</label>
      <input type="text" id="setCurrency" maxlength="10">
    </div>
    <div class="field">
      <label id="lblBackup">—</label>
      <textarea id="backupArea" class="backup-area" rows="4"></textarea>
      <div style="display:flex; gap:8px; margin-top:8px;">
        <button class="btn save" id="exportBtn">—</button>
        <button class="btn cancel" id="importBtn">—</button>
      </div>
      <div class="hint" id="hintBackup">—</div>
    </div>
    <button class="danger-btn" id="resetBtn">—</button>
  </div>

  <div class="nav">
    <button class="active" data-tab="home">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M3 11.5 12 4l9 7.5"/><path d="M5 10v9a1 1 0 0 0 1 1h4v-6h4v6h4a1 1 0 0 0 1-1v-9"/></svg>
      <span id="navHome">—</span>
    </button>
    <button data-tab="history">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 7v5l3 2"/><circle cx="12" cy="12" r="9"/></svg>
      <span id="navHistory">—</span>
    </button>
    <button data-tab="settings">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.7 1.7 0 0 0 .34 1.87l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.7 1.7 0 0 0-1.87-.34 1.7 1.7 0 0 0-1 1.55V21a2 2 0 1 1-4 0v-.09a1.7 1.7 0 0 0-1-1.55 1.7 1.7 0 0 0-1.87.34l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.7 1.7 0 0 0 .34-1.87 1.7 1.7 0 0 0-1.55-1H3a2 2 0 1 1 0-4h.09a1.7 1.7 0 0 0 1.55-1 1.7 1.7 0 0 0-.34-1.87l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.7 1.7 0 0 0 1.87.34H9a1.7 1.7 0 0 0 1-1.55V3a2 2 0 1 1 4 0v.09a1.7 1.7 0 0 0 1 1.55 1.7 1.7 0 0 0 1.87-.34l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.7 1.7 0 0 0-.34 1.87V9c.26.43.7.7 1.55 1H21a2 2 0 1 1 0 4h-.09a1.7 1.7 0 0 0-1.55 1z"/></svg>
      <span id="navSettings">—</span>
    </button>
  </div>
</div>

<div class="sheet-overlay" id="sheetOverlay">
  <div class="sheet">
    <h3 id="sheetTitle">—</h3>
    <div class="field">
      <label id="lblDayType">—</label>
      <div class="chip-row" id="dayTypeChips">
        <button class="chip" data-type="work" id="chipWork">—</button>
        <button class="chip" data-type="holiday" id="chipHoliday">—</button>
        <button class="chip" data-type="rest" id="chipRest">—</button>
        <button class="chip" data-type="absence" id="chipAbsence">—</button>
      </div>
    </div>
    <div class="field">
      <label id="lblDate">—</label>
      <input type="date" id="editDate">
    </div>
    <div id="workTimeFields">
      <div class="field">
        <label id="lblInTime">—</label>
        <input type="time" id="editIn">
      </div>
      <div class="field">
        <label id="lblOutTime">—</label>
        <input type="time" id="editOut">
      </div>
    </div>
    <div class="field" id="holidayNameField" style="display:none;">
      <label id="lblHolidayName2">—</label>
      <input type="text" id="editHolidayName" maxlength="40">
    </div>
    <div class="sheet-actions">
      <button class="btn cancel" id="sheetCancel">—</button>
      <button class="btn save" id="sheetSave">—</button>
    </div>
    <div class="sheet-actions" id="deleteRow" style="display:none;">
      <button class="btn delete" id="sheetDelete">—</button>
    </div>
  </div>
</div>

<script>
(function(){
  "use strict";

  var I18N = {
    ar: {
      dir:'rtl', fontStack:"system-ui,-apple-system,'Segoe UI','Geeza Pro',sans-serif",
      weekdays:["الأحد","الاثنين","الثلاثاء","الأربعاء","الخميس","الجمعة","السبت"],
      months:["يناير","فبراير","مارس","أبريل","مايو","يونيو","يوليو","أغسطس","سبتمبر","أكتوبر","نوفمبر","ديسمبر"],
      ampm:{am:'ص', pm:'م'}, durH:'س', durM:'د',
      notClockedIn:'لسه ما دخلتش النهارده',
      workingSince:function(t,dur){return 'في الشغل من '+t+' — '+dur;},
      workingSinceOT:function(t,dur){return 'في الشغل من '+t+' — '+dur+' (وقت إضافي)';},
      finishedToday:function(t){return 'خلصت شغل النهارده الساعة '+t;},
      clockIn:'تسجيل حضور', clockOut:'تسجيل انصراف',
      stampIn:'دخول', stampOut:'خروج',
      staleMsg:'لسه مسجل حضور من قبل كده وما اتسجلش انصراف. تحب تقفل اليوم ده؟',
      staleBtn:'تسجيل انصراف الآن',
      today:'اليوم', history:'السجل', settings:'الإعدادات',
      home:'الرئيسية',
      in:'دخول', regular:'عادي', overtime:'إضافي', overtimeValue:'قيمة الإضافي',
      emptyHistory:'لسه معملتش أي تسجيل.<br>دوس على زرار "تسجيل حضور" في الرئيسية أول ما توصل الشغل.',
      monthDays:function(n){return n+' يوم';},
      editDay:'تعديل يوم', addDay:'إضافة يوم يدوي',
      date:'التاريخ', inTime:'وقت الدخول', outTime:'وقت الخروج',
      cancel:'إلغاء', save:'حفظ', deleteDay:'حذف اليوم ده',
      language:'اللغة',
      standardHoursLabel:'ساعات الشغل الرسمية في اليوم',
      hourlyRateLabel:'سعر الساعة',
      multiplierLabel:'معامل الوقت الإضافي',
      multiplierHint:'قيمة الساعة الإضافية = سعر الساعة × المعامل ده',
      currencyLabel:'العملة',
      resetBtn:'مسح كل البيانات',
      resetConfirm:'متأكد؟ ده هيمسح كل الأيام المسجلة والإعدادات.',
      weekdaysShort:["أحد","اثنين","ثلاثاء","أربعاء","خميس","جمعة","سبت"],
      restDaysLabel:'أيام الإجازة الأسبوعية',
      holidaysLabel:'العطلات الرسمية',
      noHolidays:'لسه مفيش عطلات رسمية مضافة',
      addHoliday:'إضافة عطلة', editHoliday:'تعديل عطلة',
      holidayDateLabel:'التاريخ', holidayNameLabel:'اسم العطلة',
      workDaysLbl:'أيام شغل', totalHoursLbl:'إجمالي الساعات',
      restDaysCountLbl:'إجازة أسبوعية', holidaysCountLbl:'عطلة رسمية', absenceLbl:'غياب',
      dayTypeLabel:'نوع اليوم', workDayLabel:'يوم شغل',
      holidayNameLabel2:'اسم العطلة',
      overtimePayLbl:'قيمة الإضافي',
      workDaysSection:'أيام الشغل', holidaysSection:'العطلات الرسمية',
      restSection:'الإجازة الأسبوعية', absenceSection:'الغياب',
      lblBackup:'نسخة احتياطية', hintBackup:'لو حاسس إن البيانات بتتمسح، دوس "نسخ البيانات" واحفظ النص ده في مكان آمن (نوت أو إيميل لنفسك). لو حصل ومسحت، الصقه هنا ودوس "استرجاع".',
      exportBtn:'نسخ البيانات', importBtn:'استرجاع',
      importSuccess:'تم الاسترجاع بنجاح', importError:'النص ده مش نسخة احتياطية صحيحة',
      copiedMsg:'اتنسخ ✓'
    },
    en: {
      dir:'ltr', fontStack:"system-ui,-apple-system,'Segoe UI',sans-serif",
      weekdays:["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"],
      months:["January","February","March","April","May","June","July","August","September","October","November","December"],
      ampm:{am:'AM', pm:'PM'}, durH:'h', durM:'m',
      notClockedIn:"You haven't clocked in today",
      workingSince:function(t,dur){return 'Working since '+t+' — '+dur;},
      workingSinceOT:function(t,dur){return 'Working since '+t+' — '+dur+' (overtime)';},
      finishedToday:function(t){return 'Finished for today at '+t;},
      clockIn:'Clock In', clockOut:'Clock Out',
      stampIn:'IN', stampOut:'OUT',
      staleMsg:"You're still clocked in from before and never clocked out. Close out that day?",
      staleBtn:'Clock out now',
      today:'Today', history:'History', settings:'Settings',
      home:'Home',
      in:'Clock in', regular:'Regular', overtime:'Overtime', overtimeValue:'Overtime pay',
      emptyHistory:'No entries yet.<br>Tap "Clock In" on the Home tab as soon as you get to work.',
      monthDays:function(n){return n+(n===1?' day':' days');},
      editDay:'Edit day', addDay:'Add manual day',
      date:'Date', inTime:'Clock-in time', outTime:'Clock-out time',
      cancel:'Cancel', save:'Save', deleteDay:'Delete this day',
      language:'Language',
      standardHoursLabel:'Standard work hours per day',
      hourlyRateLabel:'Hourly rate',
      multiplierLabel:'Overtime multiplier',
      multiplierHint:'Overtime hour value = hourly rate × this multiplier',
      currencyLabel:'Currency',
      resetBtn:'Clear all data',
      resetConfirm:'Are you sure? This will delete every logged day and setting.',
      weekdaysShort:["Sun","Mon","Tue","Wed","Thu","Fri","Sat"],
      restDaysLabel:'Weekly rest day(s)',
      holidaysLabel:'Public holidays',
      noHolidays:'No public holidays added yet',
      addHoliday:'Add holiday', editHoliday:'Edit holiday',
      holidayDateLabel:'Date', holidayNameLabel:'Holiday name',
      workDaysLbl:'Work days', totalHoursLbl:'Total hours',
      restDaysCountLbl:'Weekly rest', holidaysCountLbl:'Public holiday', absenceLbl:'Absence',
      dayTypeLabel:'Day type', workDayLabel:'Work day',
      holidayNameLabel2:'Holiday name',
      overtimePayLbl:'Overtime pay',
      workDaysSection:'Work days', holidaysSection:'Public holidays',
      restSection:'Weekly rest', absenceSection:'Absence',
      lblBackup:'Backup', hintBackup:'If your data keeps disappearing, tap "Copy data" and save that text somewhere safe (a note or email to yourself). If it ever gets wiped, paste it back here and tap "Restore".',
      exportBtn:'Copy data', importBtn:'Restore',
      importSuccess:'Restored successfully', importError:'That text is not a valid backup',
      copiedMsg:'Copied ✓'
    }
  };

  var SETTINGS_KEY='wh_settings', SESSION_KEY='wh_session', ENTRIES_KEY='wh_entries', LANG_KEY='wh_lang', HOLIDAYS_KEY='wh_holidays', REST_OVERRIDES_KEY='wh_rest_overrides', ABSENCES_KEY='wh_absences';

  function loadJSON(key, fallback){
    try{ var raw = localStorage.getItem(key); if(raw===null||raw===undefined) return fallback; return JSON.parse(raw); }
    catch(e){ return fallback; }
  }
  function saveJSON(key, val){ try{ localStorage.setItem(key, JSON.stringify(val)); }catch(e){ console.error('storage error', e); } }

  var settings = loadJSON(SETTINGS_KEY, {standardHours:8, hourlyRate:0, multiplier:1.7, currency:'جنيه', restDays:[5]});
  if(!settings.restDays) settings.restDays = [5];
  var session = loadJSON(SESSION_KEY, null);
  var entries = loadJSON(ENTRIES_KEY, []);
  var holidays = loadJSON(HOLIDAYS_KEY, []);
  var restOverrides = loadJSON(REST_OVERRIDES_KEY, []);
  var absences = loadJSON(ABSENCES_KEY, []);
  var LANG = loadJSON(LANG_KEY, 'ar');
  var t = I18N[LANG];

  function pad(n){ return n<10 ? '0'+n : ''+n; }
  function dateKey(d){ return d.getFullYear()+'-'+pad(d.getMonth()+1)+'-'+pad(d.getDate()); }
  function fmtTime12(d){
    var h=d.getHours(), m=d.getMinutes(), s=d.getSeconds();
    var ampm = h>=12 ? t.ampm.pm : t.ampm.am;
    var hh = h%12; if(hh===0) hh=12;
    return {str: pad(hh)+':'+pad(m)+':'+pad(s), ampm: ampm};
  }
  function fmtTimeHM(d){
    var h=d.getHours(), m=d.getMinutes();
    var ampm = h>=12 ? t.ampm.pm : t.ampm.am;
    var hh = h%12; if(hh===0) hh=12;
    return pad(hh)+':'+pad(m)+' '+ampm;
  }
  function fmtDur(mins){
    mins = Math.max(0, Math.round(mins));
    var h = Math.floor(mins/60), m = mins%60;
    return h+t.durH+' '+pad(m)+t.durM;
  }
  function fmtMoney(v){ return (Math.round(v*100)/100).toString().replace(/\.0$/,''); }
  function computeSplit(totalMin){
    var std = (settings.standardHours||8)*60;
    return {reg: Math.min(totalMin, std), ot: Math.max(0, totalMin-std)};
  }

  function applyStaticText(){
    document.documentElement.dir = t.dir;
    document.documentElement.lang = LANG;
    document.body.style.fontFamily = t.fontStack;
    document.getElementById('punchLabel').textContent = session ? t.clockOut : t.clockIn;
    document.getElementById('staleMsg').textContent = t.staleMsg;
    document.getElementById('staleBtnLabel').textContent = t.staleBtn;
    document.getElementById('todaySectionTitle').textContent = t.today;
    document.getElementById('lblIn').textContent = t.in;
    document.getElementById('lblRegular').textContent = t.regular;
    document.getElementById('lblOvertime').textContent = t.overtime;
    document.getElementById('lblOvertimeValue').textContent = t.overtimeValue;
    document.getElementById('historySectionTitle').textContent = t.history;
    document.getElementById('settingsSectionTitle').textContent = t.settings;
    document.getElementById('lblLanguage').textContent = t.language;
    document.getElementById('lblRestDays').textContent = t.restDaysLabel;
    document.getElementById('lblHolidays').textContent = t.holidaysLabel;
    document.getElementById('lblStandardHours').textContent = t.standardHoursLabel;
    document.getElementById('lblHourlyRate').textContent = t.hourlyRateLabel;
    document.getElementById('setHourlyRate').placeholder = LANG==='ar' ? 'اختياري' : 'optional';
    document.getElementById('lblMultiplier').textContent = t.multiplierLabel;
    document.getElementById('hintMultiplier').textContent = t.multiplierHint;
    document.getElementById('lblCurrency').textContent = t.currencyLabel;
    document.getElementById('resetBtn').textContent = t.resetBtn;
    document.getElementById('navHome').textContent = t.home;
    document.getElementById('navHistory').textContent = t.history;
    document.getElementById('navSettings').textContent = t.settings;
    document.getElementById('lblDate').textContent = t.date;
    document.getElementById('lblInTime').textContent = t.inTime;
    document.getElementById('lblOutTime').textContent = t.outTime;
    document.getElementById('sheetCancel').textContent = t.cancel;
    document.getElementById('sheetSave').textContent = t.save;
    document.getElementById('sheetDelete').textContent = t.deleteDay;
    document.getElementById('langArBtn').classList.toggle('active', LANG==='ar');
    document.getElementById('langEnBtn').classList.toggle('active', LANG==='en');
    document.getElementById('lblDayType').textContent = t.dayTypeLabel;
    document.getElementById('chipWork').textContent = t.workDayLabel;
    document.getElementById('chipHoliday').textContent = t.holidaysCountLbl;
    document.getElementById('chipRest').textContent = t.restDaysCountLbl;
    document.getElementById('chipAbsence').textContent = t.absenceLbl;
    document.getElementById('lblHolidayName2').textContent = t.holidayNameLabel2;
    document.getElementById('lblBackup').textContent = t.lblBackup;
    document.getElementById('hintBackup').textContent = t.hintBackup;
    document.getElementById('exportBtn').textContent = t.exportBtn;
    document.getElementById('importBtn').textContent = t.importBtn;
    renderRestDayChips();
    renderHolidayList();
  }

  var tabs = document.querySelectorAll('.nav button');
  tabs.forEach(function(btn){
    btn.addEventListener('click', function(){
      tabs.forEach(function(b){ b.classList.remove('active'); });
      btn.classList.add('active');
      document.querySelectorAll('.tab-page').forEach(function(p){ p.classList.remove('active'); });
      document.getElementById('tab-'+btn.dataset.tab).classList.add('active');
      document.getElementById('addEntryFab').style.display = btn.dataset.tab==='history' ? 'block' : 'none';
      if(btn.dataset.tab==='history') renderHistory();
    });
  });

  var liveClockEl = document.getElementById('liveClock');
  var todayDateEl = document.getElementById('todayDate');
  var statusLine = document.getElementById('statusLine');
  var punchBtn = document.getElementById('punchBtn');
  var punchLabel = document.getElementById('punchLabel');
  var todayCard = document.getElementById('todayCard');
  var staleBanner = document.getElementById('staleBanner');

  function tick(){
    var now = new Date();
    var tm = fmtTime12(now);
    liveClockEl.innerHTML = tm.str + '<span class="ampm">'+tm.ampm+'</span>';
    todayDateEl.textContent = t.weekdays[now.getDay()] + '، ' + now.getDate() + ' ' + t.months[now.getMonth()];
    updateStatus(now);
  }

  function updateStatus(now){
    if(session && session.clockIn){
      var start = new Date(session.clockIn);
      var totalMin = (now - start)/60000;
      var split = computeSplit(totalMin);
      var elapsedStr = fmtDur(totalMin);
      punchLabel.textContent = t.clockOut;
      if(split.ot>0){
        statusLine.className='status-line overtime';
        statusLine.textContent = t.workingSinceOT(fmtTimeHM(start), elapsedStr);
        punchBtn.classList.add('overtime'); punchBtn.classList.remove('out');
      }else{
        statusLine.className='status-line working';
        statusLine.textContent = t.workingSince(fmtTimeHM(start), elapsedStr);
        punchBtn.classList.remove('overtime'); punchBtn.classList.add('out');
      }
      todayCard.style.display='block';
      document.getElementById('todayIn').textContent = fmtTimeHM(start);
      document.getElementById('todayRegular').textContent = fmtDur(split.reg);
      document.getElementById('todayOvertime').textContent = fmtDur(split.ot);
      var payRow=document.getElementById('todayPayRow');
      if(settings.hourlyRate>0){
        payRow.style.display='flex';
        document.getElementById('todayPay').textContent = fmtMoney(split.ot/60*settings.hourlyRate*settings.multiplier)+' '+settings.currency;
      }else{ payRow.style.display='none'; }
      staleBanner.classList.toggle('show', totalMin > 16*60);
    }else{
      punchBtn.classList.remove('out','overtime');
      punchLabel.textContent=t.clockIn;
      staleBanner.classList.remove('show');
      var todaysEntry = entries.filter(function(e){ return e.date===dateKey(now); }).sort(function(a,b){ return b.clockIn.localeCompare(a.clockIn); })[0];
      if(todaysEntry){
        statusLine.className='status-line';
        statusLine.textContent = t.finishedToday(fmtTimeHM(new Date(todaysEntry.clockOut)));
        todayCard.style.display='block';
        document.getElementById('todayIn').textContent = fmtTimeHM(new Date(todaysEntry.clockIn));
        document.getElementById('todayRegular').textContent = fmtDur(todaysEntry.regularMin);
        document.getElementById('todayOvertime').textContent = fmtDur(todaysEntry.overtimeMin);
        var payRow2=document.getElementById('todayPayRow');
        if(settings.hourlyRate>0){
          payRow2.style.display='flex';
          document.getElementById('todayPay').textContent = fmtMoney(todaysEntry.overtimeMin/60*settings.hourlyRate*settings.multiplier)+' '+settings.currency;
        }else{ payRow2.style.display='none'; }
      }else{
        statusLine.className='status-line';
        statusLine.textContent=t.notClockedIn;
        todayCard.style.display='none';
      }
    }
  }

  setInterval(tick, 1000);

  punchBtn.addEventListener('click', function(){
    var stamp = document.getElementById('stampMark');
    if(!session){
      session = {clockIn: new Date().toISOString()};
      saveJSON(SESSION_KEY, session);
      stamp.textContent=t.stampIn;
    }else{
      var clockIn = new Date(session.clockIn);
      var clockOut = new Date();
      var totalMin = (clockOut-clockIn)/60000;
      var split = computeSplit(totalMin);
      entries.push({
        id: Date.now().toString(36), date: dateKey(clockIn),
        clockIn: clockIn.toISOString(), clockOut: clockOut.toISOString(),
        totalMin: totalMin, regularMin: split.reg, overtimeMin: split.ot
      });
      saveJSON(ENTRIES_KEY, entries);
      session = null;
      saveJSON(SESSION_KEY, null);
      stamp.textContent=t.stampOut;
    }
    stamp.classList.remove('show'); void stamp.offsetWidth; stamp.classList.add('show');
    tick();
  });

  document.getElementById('fixStaleBtn').addEventListener('click', function(){
    var start = session ? new Date(session.clockIn) : new Date();
    var now = new Date();
    openSheet({type:'work', date:dateKey(start), inTime:pad(start.getHours())+':'+pad(start.getMinutes()), outTime:pad(now.getHours())+':'+pad(now.getMinutes())});
  });

  function renderHistory(){
    var list = document.getElementById('historyList');
    if(entries.length===0 && holidays.length===0 && restOverrides.length===0 && absences.length===0){
      list.innerHTML = '<div class="empty">'+t.emptyHistory+'</div>';
      return;
    }
    var byMonth = {};
    function pushItem(dt, item){ var key=dt.slice(0,7); (byMonth[key]=byMonth[key]||[]).push(item); }
    entries.forEach(function(e){ pushItem(e.date, {kind:'work', date:e.date, data:e}); });
    holidays.forEach(function(h){ pushItem(h.date, {kind:'holiday', date:h.date, data:h}); });
    restOverrides.forEach(function(r){ pushItem(r.date, {kind:'rest', date:r.date, data:r}); });
    absences.forEach(function(a){ pushItem(a.date, {kind:'absence', date:a.date, data:a}); });

    var html='';
    Object.keys(byMonth).sort().reverse().forEach(function(mk){
      var list_ = byMonth[mk].slice().sort(function(a,b){ return b.date.localeCompare(a.date); });
      var y=parseInt(mk.slice(0,4),10), mo=parseInt(mk.slice(5,7),10)-1;
      var monthWorkEntries = list_.filter(function(i){ return i.kind==='work'; }).map(function(i){ return i.data; });
      var totalOt=0, totalReg=0, uniqueDays={};
      monthWorkEntries.forEach(function(e){ totalOt+=e.overtimeMin; totalReg+=e.regularMin; uniqueDays[e.date]=true; });
      var workDaysCount = Object.keys(uniqueDays).length;
      var ms = computeMonthStats(y, mo, monthWorkEntries);
      html += '<div class="month-block">';
      html += '<div class="month-header"><span class="name">'+t.months[mo]+' '+y+'</span></div>';
      html += '<div class="stat-grid">';
      html += '<div class="stat-cell"><span>'+t.workDaysLbl+'</span><span class="v mono">'+workDaysCount+'</span></div>';
      html += '<div class="stat-cell"><span>'+t.totalHoursLbl+'</span><span class="v mono">'+fmtDur(totalReg+totalOt)+'</span></div>';
      html += '<div class="stat-cell"><span>'+t.overtime+'</span><span class="v o mono">'+fmtDur(totalOt)+'</span></div>';
      if(settings.hourlyRate>0){
        html += '<div class="stat-cell"><span>'+t.overtimePayLbl+'</span><span class="v o mono">'+fmtMoney(totalOt/60*settings.hourlyRate*settings.multiplier)+' '+settings.currency+'</span></div>';
      }
      html += '<div class="stat-cell"><span>'+t.restDaysCountLbl+'</span><span class="v mono">'+ms.restCount+'</span></div>';
      html += '<div class="stat-cell"><span>'+t.holidaysCountLbl+'</span><span class="v mono">'+ms.holidayCount+'</span></div>';
      html += '<div class="stat-cell"><span>'+t.absenceLbl+'</span><span class="v a mono">'+ms.absenceCount+'</span></div>';
      html += '</div>';

      function dayRowHtml(item){
        var d = new Date(item.date+'T00:00:00');
        var row = '<div class="day-row" data-kind="'+item.kind+'" data-id="'+item.data.id+'">';
        row += '<div class="left"><div class="d">'+t.weekdays[d.getDay()]+'، '+d.getDate()+'</div>';
        if(item.kind==='work'){
          row += '<div class="t mono">'+fmtTimeHM(new Date(item.data.clockIn))+' – '+fmtTimeHM(new Date(item.data.clockOut))+'</div></div>';
          row += '<div class="right"><span class="r mono">'+fmtDur(item.data.regularMin)+'</span>'+(item.data.overtimeMin>0?'<span class="o mono">+'+fmtDur(item.data.overtimeMin)+'</span>':'')+'</div>';
        }else if(item.kind==='holiday'){
          row += '<div class="t">'+item.data.name+'</div></div><div class="right"></div>';
        }else if(item.kind==='rest'){
          row += '<div class="t"></div></div><div class="right"></div>';
        }else{
          row += '<div class="t"></div></div><div class="right"></div>';
        }
        row += '</div>';
        return row;
      }

      var workItems = list_.filter(function(i){ return i.kind==='work'; });
      var holidayItems = list_.filter(function(i){ return i.kind==='holiday'; });
      var restItems = list_.filter(function(i){ return i.kind==='rest'; });
      var absenceItems = list_.filter(function(i){ return i.kind==='absence'; });

      if(workItems.length){
        html += '<div class="sub-heading">'+t.workDaysSection+'</div>';
        workItems.forEach(function(i){ html += dayRowHtml(i); });
      }
      if(holidayItems.length){
        html += '<div class="sub-heading">'+t.holidaysSection+'</div>';
        holidayItems.forEach(function(i){ html += dayRowHtml(i); });
      }
      if(restItems.length){
        html += '<div class="sub-heading">'+t.restSection+'</div>';
        restItems.forEach(function(i){ html += dayRowHtml(i); });
      }
      if(absenceItems.length){
        html += '<div class="sub-heading">'+t.absenceSection+'</div>';
        absenceItems.forEach(function(i){ html += dayRowHtml(i); });
      }
      html += '</div>';
    });
    list.innerHTML = html;
    list.querySelectorAll('.day-row').forEach(function(row){
      row.addEventListener('click', function(){
        var kind = row.dataset.kind, id = row.dataset.id;
        if(kind==='work'){
          var e = entries.find(function(x){ return x.id===id; });
          if(e) openSheet({type:'work', date:e.date, entryId:e.id, inTime:pad(new Date(e.clockIn).getHours())+':'+pad(new Date(e.clockIn).getMinutes()), outTime:pad(new Date(e.clockOut).getHours())+':'+pad(new Date(e.clockOut).getMinutes())});
        }else if(kind==='holiday'){
          var h = holidays.find(function(x){ return x.id===id; });
          if(h) openSheet({type:'holiday', date:h.date, holidayId:h.id, holidayName:h.name});
        }else if(kind==='rest'){
          var r = restOverrides.find(function(x){ return x.id===id; });
          if(r) openSheet({type:'rest', date:r.date, restId:r.id});
        }else{
          var a = absences.find(function(x){ return x.id===id; });
          if(a) openSheet({type:'absence', date:a.date, absenceId:a.id});
        }
      });
    });
  }

  document.getElementById('addEntryFab').addEventListener('click', function(){
    var now=new Date();
    openSheet({type:'work', date:dateKey(now), inTime:pad(now.getHours())+':'+pad(now.getMinutes()), outTime:pad(now.getHours())+':'+pad(now.getMinutes())});
  });

  var sheetOverlay = document.getElementById('sheetOverlay');
  var editCtx = null;
  var currentSheetType = 'work';

  function setSheetType(type){
    currentSheetType = type;
    document.querySelectorAll('#dayTypeChips .chip').forEach(function(c){ c.classList.toggle('active', c.dataset.type===type); });
    document.getElementById('workTimeFields').style.display = type==='work' ? 'block' : 'none';
    document.getElementById('holidayNameField').style.display = type==='holiday' ? 'block' : 'none';
  }
  document.querySelectorAll('#dayTypeChips .chip').forEach(function(c){
    c.addEventListener('click', function(){ setSheetType(c.dataset.type); });
  });

  function openSheet(ctx){
    editCtx = ctx || {type:'work'};
    var isEdit = !!(editCtx.entryId||editCtx.holidayId||editCtx.restId||editCtx.absenceId);
    document.getElementById('sheetTitle').textContent = isEdit ? t.editDay : t.addDay;
    setSheetType(editCtx.type||'work');
    var now = new Date();
    document.getElementById('editDate').value = editCtx.date || dateKey(now);
    document.getElementById('editIn').value = editCtx.inTime || (pad(now.getHours())+':'+pad(now.getMinutes()));
    document.getElementById('editOut').value = editCtx.outTime || (pad(now.getHours())+':'+pad(now.getMinutes()));
    document.getElementById('editHolidayName').value = editCtx.holidayName || '';
    document.getElementById('deleteRow').style.display = isEdit ? 'flex' : 'none';
    sheetOverlay.classList.add('show');
  }
  function closeSheet(){ sheetOverlay.classList.remove('show'); }
  document.getElementById('sheetCancel').addEventListener('click', closeSheet);
  sheetOverlay.addEventListener('click', function(ev){ if(ev.target===sheetOverlay) closeSheet(); });

  function clearDateAcrossStores(dateStr){
    entries = entries.filter(function(x){ return x.date!==dateStr; });
    holidays = holidays.filter(function(x){ return x.date!==dateStr; });
    restOverrides = restOverrides.filter(function(x){ return x.date!==dateStr; });
    absences = absences.filter(function(x){ return x.date!==dateStr; });
  }

  document.getElementById('sheetSave').addEventListener('click', function(){
    var dateStr = document.getElementById('editDate').value;
    if(!dateStr) return;
    var type = currentSheetType;

    if(editCtx){
      if(editCtx.entryId) entries = entries.filter(function(x){ return x.id!==editCtx.entryId; });
      if(editCtx.holidayId) holidays = holidays.filter(function(x){ return x.id!==editCtx.holidayId; });
      if(editCtx.restId) restOverrides = restOverrides.filter(function(x){ return x.id!==editCtx.restId; });
      if(editCtx.absenceId) absences = absences.filter(function(x){ return x.id!==editCtx.absenceId; });
    }
    clearDateAcrossStores(dateStr);

    if(type==='work'){
      var inStr = document.getElementById('editIn').value;
      var outStr = document.getElementById('editOut').value;
      if(!inStr || !outStr) return;
      var clockIn = new Date(dateStr+'T'+inStr+':00');
      var clockOut = new Date(dateStr+'T'+outStr+':00');
      if(clockOut <= clockIn) clockOut = new Date(clockOut.getTime()+24*60*60*1000);
      var totalMin = (clockOut-clockIn)/60000;
      var split = computeSplit(totalMin);
      entries.push({id:Date.now().toString(36), date:dateKey(clockIn), clockIn:clockIn.toISOString(), clockOut:clockOut.toISOString(), totalMin:totalMin, regularMin:split.reg, overtimeMin:split.ot});
    }else if(type==='holiday'){
      var name = document.getElementById('editHolidayName').value.trim();
      if(!name) return;
      holidays.push({id:Date.now().toString(36), date:dateStr, name:name});
    }else if(type==='rest'){
      restOverrides.push({id:Date.now().toString(36), date:dateStr});
    }else{
      absences.push({id:Date.now().toString(36), date:dateStr});
    }

    if(session){ session=null; saveJSON(SESSION_KEY,null); }
    saveJSON(ENTRIES_KEY, entries);
    saveJSON(HOLIDAYS_KEY, holidays);
    saveJSON(REST_OVERRIDES_KEY, restOverrides);
    saveJSON(ABSENCES_KEY, absences);
    closeSheet(); renderHistory(); renderHolidayList(); tick();
  });

  document.getElementById('sheetDelete').addEventListener('click', function(){
    if(editCtx){
      if(editCtx.entryId) entries = entries.filter(function(x){ return x.id!==editCtx.entryId; });
      if(editCtx.holidayId) holidays = holidays.filter(function(x){ return x.id!==editCtx.holidayId; });
      if(editCtx.restId) restOverrides = restOverrides.filter(function(x){ return x.id!==editCtx.restId; });
      if(editCtx.absenceId) absences = absences.filter(function(x){ return x.id!==editCtx.absenceId; });
    }
    saveJSON(ENTRIES_KEY, entries);
    saveJSON(HOLIDAYS_KEY, holidays);
    saveJSON(REST_OVERRIDES_KEY, restOverrides);
    saveJSON(ABSENCES_KEY, absences);
    closeSheet(); renderHistory(); renderHolidayList(); tick();
  });

  function loadSettingsUI(){
    document.getElementById('setStandardHours').value = settings.standardHours;
    document.getElementById('setHourlyRate').value = settings.hourlyRate || '';
    document.getElementById('setMultiplier').value = settings.multiplier;
    document.getElementById('setCurrency').value = settings.currency;
  }
  loadSettingsUI();
  ['setStandardHours','setHourlyRate','setMultiplier','setCurrency'].forEach(function(id){
    document.getElementById(id).addEventListener('change', function(){
      settings.standardHours = parseFloat(document.getElementById('setStandardHours').value)||8;
      settings.hourlyRate = parseFloat(document.getElementById('setHourlyRate').value)||0;
      settings.multiplier = parseFloat(document.getElementById('setMultiplier').value)||1.7;
      settings.currency = document.getElementById('setCurrency').value||'جنيه';
      saveJSON(SETTINGS_KEY, settings);
      tick();
    });
  });

  function renderRestDayChips(){
    var wrap = document.getElementById('restDayChips');
    wrap.innerHTML='';
    for(var i=0;i<7;i++){
      (function(i){
        var b = document.createElement('button');
        b.className = 'chip' + (settings.restDays.indexOf(i)>-1 ? ' active' : '');
        b.textContent = t.weekdaysShort[i];
        b.addEventListener('click', function(){
          var idx = settings.restDays.indexOf(i);
          if(idx>-1) settings.restDays.splice(idx,1); else settings.restDays.push(i);
          saveJSON(SETTINGS_KEY, settings);
          renderRestDayChips();
          renderHistory();
        });
        wrap.appendChild(b);
      })(i);
    }
  }

  function renderHolidayList(){
    var wrap = document.getElementById('holidayList');
    if(holidays.length===0){
      wrap.innerHTML = '<div class="empty-mini">'+t.noHolidays+'</div>';
      return;
    }
    var sorted = holidays.slice().sort(function(a,b){ return a.date.localeCompare(b.date); });
    wrap.innerHTML = sorted.map(function(h){
      var d = new Date(h.date+'T00:00:00');
      return '<div class="holiday-row" data-id="'+h.id+'"><span>'+h.name+'</span><span class="hd mono">'+t.weekdays[d.getDay()]+'، '+d.getDate()+' '+t.months[d.getMonth()]+'</span></div>';
    }).join('');
    wrap.querySelectorAll('.holiday-row').forEach(function(row){
      row.addEventListener('click', function(){
        var h = holidays.find(function(x){ return x.id===row.dataset.id; });
        if(h) openSheet({type:'holiday', date:h.date, holidayId:h.id, holidayName:h.name});
      });
    });
  }

  document.getElementById('addHolidayBtn').addEventListener('click', function(){
    openSheet({type:'holiday', date:dateKey(new Date())});
  });

  function computeMonthStats(year, monthIndex, monthEntries){
    var daysInMonth = new Date(year, monthIndex+1, 0).getDate();
    var today = new Date();
    var lastDay = daysInMonth;
    if(year===today.getFullYear() && monthIndex===today.getMonth()) lastDay = today.getDate();
    else if(year>today.getFullYear() || (year===today.getFullYear() && monthIndex>today.getMonth())) lastDay = 0;

    var entryDates = {};
    monthEntries.forEach(function(e){ entryDates[e.date]=true; });
    var holidayMap = {};
    holidays.forEach(function(h){ holidayMap[h.date]=true; });
    var restOverrideMap = {};
    restOverrides.forEach(function(r){ restOverrideMap[r.date]=true; });
    var absenceMap = {};
    absences.forEach(function(a){ absenceMap[a.date]=true; });

    var restCount=0, holidayCount=0, absenceCount=0;
    for(var d=1; d<=lastDay; d++){
      var dateObj = new Date(year, monthIndex, d);
      var key = dateKey(dateObj);
      if(entryDates[key]) continue;
      if(holidayMap[key]){ holidayCount++; continue; }
      if(restOverrideMap[key]){ restCount++; continue; }
      if(absenceMap[key]){ absenceCount++; continue; }
      if(settings.restDays.indexOf(dateObj.getDay())>-1){ restCount++; continue; }
      absenceCount++;
    }
    return {restCount:restCount, holidayCount:holidayCount, absenceCount:absenceCount};
  }

  function setLang(newLang){
    LANG = newLang; t = I18N[LANG];
    saveJSON(LANG_KEY, LANG);
    applyStaticText();
    renderHistory();
    tick();
  }
  document.getElementById('langArBtn').addEventListener('click', function(){ setLang('ar'); });
  document.getElementById('langEnBtn').addEventListener('click', function(){ setLang('en'); });

  document.getElementById('exportBtn').addEventListener('click', function(){
    var backup = {settings:settings, entries:entries, holidays:holidays, restOverrides:restOverrides, absences:absences};
    var json = JSON.stringify(backup);
    document.getElementById('backupArea').value = json;
    var btn = document.getElementById('exportBtn');
    var original = btn.textContent;
    function showCopied(){ btn.textContent = t.copiedMsg; setTimeout(function(){ btn.textContent = original; }, 1500); }
    if(navigator.clipboard && navigator.clipboard.writeText){
      navigator.clipboard.writeText(json).then(showCopied).catch(function(){
        document.getElementById('backupArea').select();
      });
    }else{
      document.getElementById('backupArea').select();
      try{ document.execCommand('copy'); showCopied(); }catch(e){}
    }
  });
  document.getElementById('importBtn').addEventListener('click', function(){
    var raw = document.getElementById('backupArea').value;
    if(!raw || !raw.trim()){ alert(t.importError); return; }
    raw = raw.trim()
      .replace(/[\u201C\u201D\u201F\u2033]/g, '"')
      .replace(/[\u2018\u2019\u2032]/g, "'")
      .replace(/\u00A0/g, ' ');
    try{
      var data = JSON.parse(raw);
      if(data.settings) settings = data.settings;
      if(!settings.restDays) settings.restDays=[5];
      if(data.entries) entries = data.entries;
      if(data.holidays) holidays = data.holidays;
      if(data.restOverrides) restOverrides = data.restOverrides;
      if(data.absences) absences = data.absences;
      saveJSON(SETTINGS_KEY, settings);
      saveJSON(ENTRIES_KEY, entries);
      saveJSON(HOLIDAYS_KEY, holidays);
      saveJSON(REST_OVERRIDES_KEY, restOverrides);
      saveJSON(ABSENCES_KEY, absences);
      loadSettingsUI(); renderRestDayChips(); renderHolidayList(); renderHistory(); tick();
      alert(t.importSuccess);
    }catch(e){
      alert(t.importError + '\n\n' + e.message);
    }
  });

  document.getElementById('resetBtn').addEventListener('click', function(){
    if(confirm(t.resetConfirm)){
      try{
        localStorage.removeItem(SETTINGS_KEY);
        localStorage.removeItem(SESSION_KEY);
        localStorage.removeItem(ENTRIES_KEY);
        localStorage.removeItem(HOLIDAYS_KEY);
        localStorage.removeItem(REST_OVERRIDES_KEY);
        localStorage.removeItem(ABSENCES_KEY);
      }catch(e){}
      settings = {standardHours:8, hourlyRate:0, multiplier:1.7, currency:'جنيه', restDays:[5]};
      session = null; entries = []; holidays = []; restOverrides = []; absences = [];
      loadSettingsUI(); renderRestDayChips(); renderHolidayList(); renderHistory(); tick();
    }
  });

  applyStaticText();
  renderRestDayChips();
  renderHolidayList();
  tick();
})();
</script>
</body>
</html>
