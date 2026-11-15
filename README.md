<!DOCTYPE ht
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">

<meta name="theme-color" content="#0B0D12">
<meta name="color-scheme" content="dark">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content=" ">
<link rel="apple-touch-icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 180 180'%3E%3Crect width='180' height='180' rx='36' fill='%230B0D12'/%3E%3Ccircle cx='90' cy='96' r='58' fill='none' stroke='%23C8F25A' stroke-width='9'/%3E%3Cline x1='90' y1='96' x2='90' y2='58' stroke='%23EFE9DA' stroke-width='8' stroke-linecap='round'/%3E%3Cline x1='90' y1='96' x2='118' y2='104' stroke='%23EFE9DA' stroke-width='8' stroke-linecap='round'/%3E%3Crect x='72' y='22' width='36' height='16' rx='6' fill='%23C8F25A'/%3E%3C/svg%3E">
<style>
:root{color-scheme:dark;--bg:#0B0D12;--surface:#141821;--surface2:#1C2230;--ink:#F2F4F8;--ink-soft:#8A93A6;--line:#232A3A;--accent:#C8F25A;--accent-ink:#0B0D12;--regular:#C8F25A;--overtime:#FF7A59;--overtime-soft:#2A1A17;--danger:#FF6B6B;--morning:#FFC857;--evening:#7C9CFF;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);box-sizing:border-box}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{height:100%}
body{margin:0;background:var(--bg);color:var(--ink);font-family:system-ui,-apple-system,'Segoe UI','Geeza Pro',sans-serif;min-height:100%;-webkit-font-smoothing:antialiased;overflow-x:hidden}
.mono{font-family:ui-monospace,'SF Mono',Menlo,Consolas,monospace;font-variant-numeric:tabular-nums}
.app{max-width:480px;margin:0 auto;min-height:100%;position:relative}
.tab-page{display:none;padding:16px 16px 130px}.tab-page.active{display:block}
.datebar{text-align:start;font-size:22px;font-weight:800;padding:10px 4px 0}
.ringwrap{position:relative;width:min(70vw,250px);aspect-ratio:1;margin:16px auto 6px}
.ringwrap svg{width:100%;height:100%;display:block}
.rt{fill:none;stroke:var(--surface2);stroke-width:12}
.rp{fill:none;stroke:var(--accent);stroke-width:12;stroke-linecap:round;stroke-dasharray:615.75;stroke-dashoffset:615.75;transition:stroke-dashoffset .6s ease,stroke .3s}
.rp.ot{stroke:var(--overtime)}
.ringin{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center}
.clock{font-size:36px;font-weight:700;line-height:1;direction:ltr;text-align:center}
.ampm{display:block;font-size:13px;color:var(--ink-soft);margin-top:6px;letter-spacing:1px}
.status-line{text-align:center;margin:8px 0 0;font-size:14px;color:var(--ink-soft);min-height:20px}
.status-line.working{color:var(--regular)}.status-line.overtime{color:var(--overtime)}
.seg{display:flex;background:var(--surface);border:1px solid var(--line);border-radius:999px;padding:4px;gap:4px;margin:16px 0}
.seg button{flex:1;padding:11px;border:none;border-radius:999px;background:none;color:var(--ink-soft);font-weight:700;font-size:14px;font-family:inherit}
.seg button.active[data-shift=morning]{background:var(--morning);color:#1A1200}
.seg button.active[data-shift=evening]{background:var(--evening);color:#06102E}
.punch-btn{width:100%;padding:20px;border:none;border-radius:999px;font-size:18px;font-weight:800;background:var(--accent);color:var(--accent-ink);cursor:pointer;position:relative;overflow:hidden;transition:transform .12s,background .3s;font-family:inherit}
.punch-btn.out{background:var(--surface2);color:var(--ink);border:1px solid var(--line)}
.punch-btn.overtime{background:var(--overtime);color:#2A0E05}
.punch-btn:active{transform:scale(.97)}
.stamp-mark{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:14px;font-weight:800;letter-spacing:1px;background:rgba(255,255,255,.2);opacity:0;pointer-events:none}
@keyframes sf{0%{opacity:1;transform:scale(1.3) rotate(-8deg)}100%{opacity:0;transform:scale(1) rotate(-8deg)}}
.stamp-mark.show{animation:sf .55s ease-out forwards}
.banner{margin-top:14px;padding:14px 16px;background:var(--overtime-soft);border:1px solid var(--overtime);border-radius:18px;font-size:14px;color:var(--overtime);display:none}
.banner.show{display:block}
.banner button{display:block;margin-top:8px;background:none;border:1px solid var(--overtime);color:var(--overtime);padding:6px 14px;border-radius:99px;font-weight:700;font-size:13px;font-family:inherit}
.section-title{font-size:28px;font-weight:800;color:var(--ink);padding:10px 4px 14px}
.today-card{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:16px}
.today-row{display:flex;flex-direction:column;gap:6px;background:var(--surface);border:1px solid var(--line);border-radius:18px;padding:12px;font-size:12px;color:var(--ink-soft)}
.today-row .val{font-size:15px;font-weight:700;color:var(--ink)}
.val.regular{color:var(--regular)!important}.val.overtime{color:var(--overtime)!important}
#todayPayRow{grid-column:1/-1;flex-direction:row;justify-content:space-between;align-items:center}
.month-block{background:var(--surface);border:1px solid var(--line);border-radius:24px;padding:16px;margin-bottom:16px}
.month-header{display:flex;margin-bottom:10px}.month-header .name{font-size:20px;font-weight:800}
.chart{margin:6px 0 14px;background:var(--surface2);border-radius:16px;padding:10px}.chart svg{width:100%;height:auto;display:block;direction:ltr}
.chart .lg{display:flex;gap:14px;font-size:11px;color:var(--ink-soft);margin-top:4px}
.chart .lg i{display:inline-block;width:8px;height:8px;border-radius:99px;margin-inline-end:4px}
.stat-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:10px}
.stat-cell{display:flex;flex-direction:column;gap:4px;background:var(--surface2);border-radius:14px;padding:10px 12px;font-size:12px;color:var(--ink-soft)}
.stat-cell .v{font-size:16px;font-weight:700;color:var(--ink)}.v.o{color:var(--overtime)!important}.v.a{color:var(--danger)!important}
.sub-heading{font-size:12px;font-weight:700;color:var(--ink-soft);margin:16px 2px 8px}
.day-row{display:flex;justify-content:space-between;align-items:center;padding:12px 14px;margin-bottom:8px;background:var(--surface2);border-radius:14px;border-inline-start:4px solid var(--regular);cursor:pointer}
.day-row[data-kind=holiday]{border-color:var(--evening)}.day-row[data-kind=rest]{border-color:var(--ink-soft)}.day-row[data-kind=absence]{border-color:var(--danger)}
.day-row .d{font-size:15px;font-weight:600}.day-row .t{font-size:12px;color:var(--ink-soft);margin-top:3px}
.day-row .right{text-align:end;font-size:14px}.day-row .r{color:var(--regular)}.day-row .o{color:var(--overtime);margin-inline-start:8px}
.badge{font-size:11px;font-weight:700;padding:2px 8px;border-radius:99px;margin-inline-start:6px}
.badge.morning{background:rgba(255,200,87,.15);color:var(--morning)}.badge.evening{background:rgba(124,156,255,.15);color:var(--evening)}
.empty{text-align:center;color:var(--ink-soft);padding:40px 10px;font-size:14px;line-height:1.9}
.fab{position:fixed;inset-inline-end:20px;bottom:calc(96px + env(safe-area-inset-bottom,0px));width:56px;height:56px;border-radius:20px;background:var(--accent);color:var(--accent-ink);border:none;font-size:28px;font-weight:700;box-shadow:0 8px 24px rgba(0,0,0,.5)}
.tools{display:flex;gap:8px;margin-bottom:14px}
.tools button{flex:1;padding:11px;border-radius:99px;border:1px solid var(--line);background:var(--surface);color:var(--ink);font-size:13px;font-weight:700;font-family:inherit}
.field{margin-bottom:16px}.field>label{display:block;font-size:13px;font-weight:600;color:var(--ink-soft);margin-bottom:8px}
.field input[type=number],.field input[type=text],.field input[type=date],.field input[type=time]{width:100%;padding:13px 16px;border-radius:14px;border:1px solid var(--line);background:var(--surface);color:var(--ink);font-size:16px;font-family:inherit}
.field .hint{font-size:12px;color:var(--ink-soft);margin-top:6px;line-height:1.6}
.danger-btn{width:100%;padding:14px;border-radius:99px;border:1px solid var(--danger);background:none;color:var(--danger);font-weight:700;font-size:15px;margin-top:10px;font-family:inherit}
.lang-toggle{display:flex;background:var(--surface);border:1px solid var(--line);border-radius:99px;padding:4px;gap:4px}
.lang-toggle button{flex:1;padding:10px;border:none;border-radius:99px;background:none;color:var(--ink-soft);font-size:14px;font-weight:700;font-family:inherit}
.lang-toggle button.active,.chip.active{background:var(--accent);color:var(--accent-ink)}
.chip-row{display:flex;flex-wrap:wrap;gap:8px}
.chip{padding:9px 16px;border-radius:99px;border:1px solid var(--line);background:var(--surface);color:var(--ink-soft);font-size:13px;font-weight:600;font-family:inherit}
.chip.active{border-color:var(--accent)}
.field-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px}.field-header label{margin:0;font-size:13px;font-weight:600;color:var(--ink-soft)}
.small-add{border:none;background:var(--accent);color:var(--accent-ink);width:30px;height:30px;border-radius:10px;font-size:18px;line-height:1}
.holiday-row{display:flex;justify-content:space-between;align-items:center;padding:12px 14px;margin-bottom:6px;background:var(--surface);border-radius:14px;font-size:14px;cursor:pointer}
.holiday-row .hd{color:var(--ink-soft);font-size:12px}.empty-mini{color:var(--ink-soft);font-size:13px;padding:8px 0}
.times,.twin{display:flex;gap:10px}.times{margin-top:10px}.times>div,.twin>div{flex:1}.times label,.twin label{display:block;font-size:12px;color:var(--ink-soft);margin-bottom:6px}
textarea.backup-area{width:100%;font-family:ui-monospace,Menlo,monospace;font-size:12px;padding:12px;border-radius:14px;border:1px solid var(--line);background:var(--surface);color:var(--ink);resize:vertical}
.nav{position:fixed;bottom:calc(10px + env(safe-area-inset-bottom,0px));left:12px;right:12px;background:rgba(20,24,33,.92);backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);border:1px solid var(--line);border-radius:28px;padding:6px;display:flex;gap:4px;max-width:456px;margin:0 auto;z-index:20}
.nav button{flex:1;background:none;border:none;padding:9px 4px;border-radius:22px;display:flex;flex-direction:column;align-items:center;gap:3px;color:var(--ink-soft);font-size:11px;font-weight:700;font-family:inherit}
.nav button.active{background:var(--accent);color:var(--accent-ink)}.nav svg{width:21px;height:21px}
.sheet-overlay{position:fixed;inset:0;background:rgba(0,0,0,.65);display:none;align-items:flex-end;justify-content:center;z-index:50}
.sheet-overlay.show{display:flex}
.sheet{background:var(--surface);width:100%;max-width:480px;max-height:92%;overflow-y:auto;border-radius:28px 28px 0 0;padding:14px 20px calc(24px + env(safe-area-inset-bottom,0px))}
.sheet::before{content:"";display:block;width:40px;height:4px;border-radius:9px;background:var(--line);margin:0 auto 16px}
.sheet h3{margin:0 0 16px;font-size:20px}
.sheet .seg{margin:0}
.sheet-actions{display:flex;gap:10px;margin-top:8px}
.btn{flex:1;padding:14px;border-radius:99px;border:none;font-weight:700;font-size:15px;font-family:inherit}
.btn.save{background:var(--accent);color:var(--accent-ink)}.btn.cancel{background:var(--surface2);color:var(--ink)}
.btn.delete{background:none;color:var(--danger);border:1px solid var(--danger)}
#printArea{display:none}
@media print{
  body{background:#fff}.app,.sheet-overlay{display:none!important}
  #printArea{display:block;color:#000;background:#fff;font-family:system-ui,'Segoe UI',sans-serif;padding:8px;direction:inherit}
  #printArea h1{font-size:20px;margin:0 0 12px}#printArea h2{font-size:15px;margin:18px 0 6px}
  #printArea table{width:100%;border-collapse:collapse;font-size:12px}
  #printArea th,#printArea td{border:1px solid #999;padding:4px 6px;text-align:start}
  #printArea th{background:#eee}
}
</style>
</head>
<body>
<div class="app">
  <div class="tab-page active" id="tab-home">
    <div class="datebar" id="todayDate">—</div>
    <div class="ringwrap"><svg viewBox="0 0 220 220"><circle class="rt" cx="110" cy="110" r="98"/><circle class="rp" id="ringP" cx="110" cy="110" r="98" transform="rotate(-90 110 110)"/></svg><div class="ringin"><div class="clock mono" id="liveClock">00:00:00</div></div></div><div class="status-line" id="statusLine">—</div>
    <div class="seg" id="shiftSeg"><button data-shift="morning" data-i="shiftMorning">—</button><button data-shift="evening" data-i="shiftEvening">—</button></div>
    <button class="punch-btn" id="punchBtn"><span id="punchLabel">—</span><span class="stamp-mark" id="stampMark"></span></button>
    <div class="banner" id="staleBanner"><span id="staleMsg">—</span><button id="fixStaleBtn" data-i="staleBtn">—</button></div>
    <div class="banner" id="remindBanner"><span id="remindMsg">—</span><button id="remindClose" data-i="dismiss">—</button></div>
    <div class="card today-card" id="todayCard" style="display:none">
      <div class="today-row"><span data-i="in">—</span><span class="val mono" id="todayIn">—</span></div>
      <div class="today-row"><span data-i="regular">—</span><span class="val regular mono" id="todayRegular">—</span></div>
      <div class="today-row"><span data-i="overtime">—</span><span class="val overtime mono" id="todayOvertime">—</span></div>
      <div class="today-row" id="todayPayRow" style="display:none"><span data-i="overtimeValue">—</span><span class="val overtime mono" id="todayPay">—</span></div>
    </div>
  </div>

  <div class="tab-page" id="tab-history">
    <div class="section-title" data-i="history">—</div>
    <div class="tools"><button id="csvBtn" data-i="exportCsv">—</button><button id="pdfBtn" data-i="exportPdf">—</button></div>
    <div id="historyList"></div>
  </div>
  <button class="fab" id="addEntryFab" style="display:none">+</button>

  <div class="tab-page" id="tab-settings">
    <div class="section-title" data-i="settings">—</div>
    <div class="field"><label data-i="language">—</label><div class="lang-toggle"><button id="langArBtn">العربية</button><button id="langEnBtn">English</button></div></div>
    <div class="field"><label data-i="restDaysLabel">—</label><div class="chip-row" id="restDayChips"></div></div>
    <div class="field"><div class="field-header"><label data-i="holidaysLabel">—</label><button class="small-add" id="addHolidayBtn">+</button></div><div id="holidayList"></div></div>
    <div class="field"><label data-i="shiftLabel">—</label><div class="twin"><div><label data-i="morningHoursLabel">—</label><input type="number" id="setMorningHours" step="0.5" min="1" max="16"></div><div><label data-i="eveningHoursLabel">—</label><input type="number" id="setEveningHours" step="0.5" min="1" max="16"></div></div><div class="hint" data-i="shiftHint">—</div></div>
    <div class="field"><label data-i="comprehensiveSalaryLabel">—</label><input type="number" id="setComprehensiveSalary" step="0.5" min="0"><div class="hint" data-i="comprehensiveSalaryHint">—</div></div>
    <div class="field"><label data-i="insuranceWageLabel">—</label><input type="number" id="setInsuranceWage" step="0.5" min="0"><div class="hint" data-i="insuranceWageHint">—</div></div>
    <div class="field"><label data-i="multiplierLabel">—</label><input type="number" id="setMultiplier" step="0.1" min="1"><div class="hint" data-i="multiplierHint">—</div></div>
    <div class="field"><label data-i="currencyLabel">—</label><input type="text" id="setCurrency" maxlength="10"></div>
    <div class="field">
      <div class="field-header"><label data-i="remindLabel">—</label><button class="chip" id="remindToggle">—</button></div>
      <div class="times"><div><label data-i="remindIn">—</label><input type="time" id="remInT"></div><div><label data-i="remindOut">—</label><input type="time" id="remOutT"></div></div>
      <div class="hint" data-i="remindHint">—</div>
    </div>
    <div class="field"><label data-i="lblBackup">—</label><textarea id="backupArea" class="backup-area" rows="4"></textarea>
      <div style="display:flex;gap:8px;margin-top:8px"><button class="btn save" id="exportBtn" data-i="exportBtn">—</button><button class="btn cancel" id="importBtn" data-i="importBtn">—</button></div>
      <div class="hint" data-i="hintBackup">—</div></div>
    <button class="danger-btn" id="resetBtn" data-i="resetBtn">—</button>
  </div>

  <div class="nav">
    <button class="active" data-tab="home"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M3 11.5 12 4l9 7.5"/><path d="M5 10v9a1 1 0 0 0 1 1h4v-6h4v6h4a1 1 0 0 0 1-1v-9"/></svg><span data-i="home">—</span></button>
    <button data-tab="history"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 7v5l3 2"/><circle cx="12" cy="12" r="9"/></svg><span data-i="history">—</span></button>
    <button data-tab="settings"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"/><path d="M12 2v3M12 19v3M2 12h3M19 12h3M4.9 4.9l2.1 2.1M17 17l2.1 2.1M4.9 19.1 7 17M17 7l2.1-2.1"/></svg><span data-i="settings">—</span></button>
  </div>
</div>

<div class="sheet-overlay" id="sheetOverlay"><div class="sheet">
  <h3 id="sheetTitle">—</h3>
  <div class="field"><label data-i="dayTypeLabel">—</label><div class="chip-row" id="dayTypeChips">
    <button class="chip" data-type="work" data-i="workDayLabel">—</button><button class="chip" data-type="holiday" data-i="holidaysCountLbl">—</button>
    <button class="chip" data-type="rest" data-i="restDaysCountLbl">—</button><button class="chip" data-type="absence" data-i="absenceLbl">—</button></div></div>
  <div class="field"><label data-i="date">—</label><input type="date" id="editDate"></div>
  <div id="workTimeFields">
    <div class="field"><label data-i="shiftLabel">—</label><div class="seg" id="sheetShiftSeg"><button data-shift="morning" data-i="shiftMorning">—</button><button data-shift="evening" data-i="shiftEvening">—</button></div></div>
    <div class="field"><label data-i="inTime">—</label><input type="time" id="editIn"></div>
    <div class="field"><label data-i="outTime">—</label><input type="time" id="editOut"></div>
  </div>
  <div class="field" id="holidayNameField" style="display:none"><label data-i="holidayNameLabel">—</label><input type="text" id="editHolidayName" maxlength="40"></div>
  <div class="sheet-actions"><button class="btn cancel" id="sheetCancel" data-i="cancel">—</button><button class="btn save" id="sheetSave" data-i="save">—</button></div>
  <div class="sheet-actions" id="deleteRow" style="display:none"><button class="btn delete" id="sheetDelete" data-i="deleteDay">—</button></div>
</div></div>
<div id="printArea"></div>

<script>
(function(){
"use strict";
var I18N={
ar:{dir:'rtl',comma:'، ',
 weekdays:["الأحد","الاثنين","الثلاثاء","الأربعاء","الخميس","الجمعة","السبت"],
 months:["يناير","فبراير","مارس","أبريل","مايو","يونيو","يوليو","أغسطس","سبتمبر","أكتوبر","نوفمبر","ديسمبر"],
 weekdaysShort:["أحد","اثنين","ثلاثاء","أربعاء","خميس","جمعة","سبت"],
 ampm:{am:'ص',pm:'م'},durH:'س',durM:'د',
 notClockedIn:'لسه ما دخلتش النهارده',
 workingSince:function(t,d){return 'في الشغل من '+t+' — '+d},
 workingSinceOT:function(t,d){return 'في الشغل من '+t+' — '+d+' (وقت إضافي)'},
 finishedToday:function(t){return 'خلصت شغل النهارده الساعة '+t},
 clockIn:'تسجيل حضور',clockOut:'تسجيل انصراف',stampIn:'دخول',stampOut:'خروج',
 staleMsg:'لسه مسجل حضور من قبل كده وما اتسجلش انصراف. تحب تقفل اليوم ده؟',staleBtn:'تسجيل انصراف الآن',
 today:'اليوم',history:'السجل',settings:'الإعدادات',home:'الرئيسية',
 in:'دخول',regular:'عادي',overtime:'إضافي',overtimeValue:'قيمة الإضافي',
 emptyHistory:'لسه معملتش أي تسجيل.<br>دوس على زرار "تسجيل حضور" في الرئيسية أول ما توصل الشغل.',
 editDay:'تعديل يوم',addDay:'إضافة يوم يدوي',date:'التاريخ',inTime:'وقت الدخول',outTime:'وقت الخروج',
 cancel:'إلغاء',save:'حفظ',deleteDay:'حذف اليوم ده',language:'اللغة',
 standardHoursLabel:'ساعات الشغل الرسمية في اليوم',
 comprehensiveSalaryLabel:'الراتب الشامل',comprehensiveSalaryHint:'الراتب الكلي شهريًا، بيتحسب عليه قيمة أيام الشغل والعطلات والإجازات المدفوعة',
 insuranceWageLabel:'الأجر التأميني',insuranceWageHint:'الأجر الأساسي اللي بيتحسب عليه الوقت الإضافي',
 workDaysPayLbl:'قيمة أيام الشغل',holidaysPayLbl:'قيمة العطلات الرسمية',restPayLbl:'قيمة الإجازات المدفوعة',
 absenceDeductionLbl:'خصم الغياب',totalSalaryDueLbl:'إجمالي الراتب المستحق',grandTotalLbl:'الإجمالي الكلي (راتب + إضافي)',
 multiplierLabel:'معامل الوقت الإضافي',multiplierHint:'قيمة الساعة الإضافية = سعر الساعة × المعامل ده',
 currencyLabel:'العملة',resetBtn:'مسح كل البيانات',resetConfirm:'متأكد؟ ده هيمسح كل الأيام المسجلة والإعدادات.',
 restDaysLabel:'أيام الإجازة الأسبوعية',holidaysLabel:'العطلات الرسمية',noHolidays:'لسه مفيش عطلات رسمية مضافة',
 holidayNameLabel:'اسم العطلة',workDaysLbl:'أيام شغل',totalHoursLbl:'إجمالي الساعات',
 restDaysCountLbl:'إجازة أسبوعية',holidaysCountLbl:'عطلة رسمية',absenceLbl:'غياب',
 dayTypeLabel:'نوع اليوم',workDayLabel:'يوم شغل',overtimePayLbl:'قيمة الإضافي',
 workDaysSection:'أيام الشغل',holidaysSection:'العطلات الرسمية',restSection:'الإجازة الأسبوعية',absenceSection:'الغياب',
 lblBackup:'نسخة احتياطية',hintBackup:'لو حاسس إن البيانات بتتمسح، دوس "نسخ البيانات" واحفظ النص ده في مكان آمن (نوت أو إيميل لنفسك). لو حصل ومسحت، الصقه هنا ودوس "استرجاع".',
 exportBtn:'نسخ البيانات',importBtn:'استرجاع',importSuccess:'تم الاسترجاع بنجاح',importError:'النص ده مش نسخة احتياطية صحيحة',copiedMsg:'اتنسخ ✓',
 exportCsv:'تصدير Excel',exportPdf:'تصدير PDF',reportTitle:'تقرير ساعات الشغل',hoursUnit:'ساعات',
 pdfNote:'اختار "حفظ كـ PDF" من شاشة الطباعة',noData:'مفيش بيانات للتصدير',
 remindLabel:'تذكيرات الحضور والانصراف',remindIn:'تذكير الحضور',remindOut:'تذكير الانصراف',
 remindHint:'التذكير بيشتغل والتطبيق مفتوح (أو أول ما تفتحه). المتصفحات مبتسمحش بتنبيهات والتطبيق مقفول تمامًا.',
 remindOn:'مفعّل',remindOff:'متوقف',dismiss:'تمام',
 remindInMsg:'⏰ وقت الحضور! متنساش تسجّل دخولك.',remindOutMsg:'⏰ وقت الانصراف! متنساش تسجّل خروجك.',
 notifDenied:'التنبيهات مقفولة من إعدادات المتصفح، هتظهرلك التذكيرات جوه التطبيق بس.',
 placeholder:'اختياري',shiftMorning:'☀️ صباحية',shiftEvening:'🌙 مسائية',shiftLabel:'الوردية',morningHoursLabel:'ساعات الصباحية',eveningHoursLabel:'ساعات المسائية',shiftHint:'الوقت الإضافي بيتحسب بعد ساعات الوردية اللي اخترتها لليوم.'},
en:{dir:'ltr',comma:', ',
 weekdays:["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"],
 months:["January","February","March","April","May","June","July","August","September","October","November","December"],
 weekdaysShort:["Sun","Mon","Tue","Wed","Thu","Fri","Sat"],
 ampm:{am:'AM',pm:'PM'},durH:'h',durM:'m',
 notClockedIn:"You haven't clocked in today",
 workingSince:function(t,d){return 'Working since '+t+' — '+d},
 workingSinceOT:function(t,d){return 'Working since '+t+' — '+d+' (overtime)'},
 finishedToday:function(t){return 'Finished for today at '+t},
 clockIn:'Clock In',clockOut:'Clock Out',stampIn:'IN',stampOut:'OUT',
 staleMsg:"You're still clocked in from before and never clocked out. Close out that day?",staleBtn:'Clock out now',
 today:'Today',history:'History',settings:'Settings',home:'Home',
 in:'Clock in',regular:'Regular',overtime:'Overtime',overtimeValue:'Overtime pay',
 emptyHistory:'No entries yet.<br>Tap "Clock In" on the Home tab as soon as you get to work.',
 editDay:'Edit day',addDay:'Add manual day',date:'Date',inTime:'Clock-in time',outTime:'Clock-out time',
 cancel:'Cancel',save:'Save',deleteDay:'Delete this day',language:'Language',
 standardHoursLabel:'Standard work hours per day',
 comprehensiveSalaryLabel:'Comprehensive salary',comprehensiveSalaryHint:'Total monthly salary; used to value work days, holidays and paid leave',
 insuranceWageLabel:'Insurance wage',insuranceWageHint:'Base wage used to calculate overtime pay',
 workDaysPayLbl:'Work days pay',holidaysPayLbl:'Public holidays pay',restPayLbl:'Paid leave pay',
 absenceDeductionLbl:'Absence deduction',totalSalaryDueLbl:'Total salary due',grandTotalLbl:'Grand total (salary + overtime)',
 multiplierLabel:'Overtime multiplier',multiplierHint:'Overtime hour value = hourly rate × this multiplier',
 currencyLabel:'Currency',resetBtn:'Clear all data',resetConfirm:'Are you sure? This will delete every logged day and setting.',
 restDaysLabel:'Weekly rest day(s)',holidaysLabel:'Public holidays',noHolidays:'No public holidays added yet',
 holidayNameLabel:'Holiday name',workDaysLbl:'Work days',totalHoursLbl:'Total hours',
 restDaysCountLbl:'Weekly rest',holidaysCountLbl:'Public holiday',absenceLbl:'Absence',
 dayTypeLabel:'Day type',workDayLabel:'Work day',overtimePayLbl:'Overtime pay',
 workDaysSection:'Work days',holidaysSection:'Public holidays',restSection:'Weekly rest',absenceSection:'Absence',
 lblBackup:'Backup',hintBackup:'If your data keeps disappearing, tap "Copy data" and save that text somewhere safe (a note or email to yourself). If it ever gets wiped, paste it back here and tap "Restore".',
 exportBtn:'Copy data',importBtn:'Restore',importSuccess:'Restored successfully',importError:'That text is not a valid backup',copiedMsg:'Copied ✓',
 exportCsv:'Export Excel',exportPdf:'Export PDF',reportTitle:'Work Hours Report',hoursUnit:'hours',
 pdfNote:'Choose "Save as PDF" in the print dialog',noData:'No data to export',
 remindLabel:'Clock in/out reminders',remindIn:'Clock-in reminder',remindOut:'Clock-out reminder',
 remindHint:'Reminders fire while the app is open (or as soon as you open it). Browsers do not allow alerts when the app is fully closed.',
 remindOn:'On',remindOff:'Off',dismiss:'OK',
 remindInMsg:"⏰ Time to clock in!",remindOutMsg:"⏰ Time to clock out!",
 notifDenied:'Notifications are blocked in browser settings; reminders will show inside the app only.',
 placeholder:'optional',shiftMorning:'☀️ Morning',shiftEvening:'🌙 Evening',shiftLabel:'Shift',morningHoursLabel:'Morning shift hours',eveningHoursLabel:'Evening shift hours',shiftHint:'Overtime is counted after the hours of the shift chosen for that day.'}
};
var K={s:'wh_settings',ses:'wh_session',e:'wh_entries',l:'wh_lang',h:'wh_holidays',r:'wh_rest_overrides',a:'wh_absences',f:'wh_fired'};
function load(k,fb){try{var r=localStorage.getItem(k);return r==null?fb:JSON.parse(r)}catch(e){return fb}}
function save(k,v){try{localStorage.setItem(k,JSON.stringify(v))}catch(e){}}
function arr(k){var v=load(k,[]);return Array.isArray(v)?v.filter(validDate):[]}
function validDate(x){return x&&typeof x.date==='string'&&x.date.length>=7}
function $(id){return document.getElementById(id)}
function esc(s){return String(s==null?'':s).replace(/[&<>"']/g,function(c){return{'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]})}

var DEF={standardHours:8,morningHours:9,eveningHours:8,comprehensiveSalary:0,insuranceWage:0,multiplier:1.7,currency:'جنيه',restDays:[5],remind:{on:false,inT:'09:00',outT:'17:00'}};
var settings=Object.assign({},DEF,load(K.s,{}));
if(!Array.isArray(settings.restDays))settings.restDays=[5];
settings.remind=Object.assign({},DEF.remind,settings.remind||{});
var session=load(K.ses,null);
var entries=arr(K.e),holidays=arr(K.h),restOverrides=arr(K.r),absences=arr(K.a);
var fired=load(K.f,{});
var LANG=load(K.l,'ar'); if(!I18N[LANG])LANG='ar';
var t=I18N[LANG];

function pad(n){return n<10?'0'+n:''+n}
function dateKey(d){return d.getFullYear()+'-'+pad(d.getMonth()+1)+'-'+pad(d.getDate())}
function hm12(d){var h=d.getHours(),hh=h%12||12;return{h:pad(hh)+':'+pad(d.getMinutes()),ap:h>=12?t.ampm.pm:t.ampm.am}}
function fmtTimeHM(d){var x=hm12(d);return x.h+' '+x.ap}
function fmtDur(m){m=Math.max(0,Math.round(m));return Math.floor(m/60)+t.durH+' '+pad(m%60)+t.durM}
function fmtMoney(v){return String(Math.round(v*100)/100)}
function shiftHours(sh){return (sh==='morning'?settings.morningHours:sh==='evening'?settings.eveningHours:settings.standardHours)||8}
function shiftName(sh){return sh==='morning'?t.shiftMorning:sh==='evening'?t.shiftEvening:''}
function autoShift(h){return h<14?'morning':'evening'}
var curShift=autoShift(new Date().getHours());
function split(total,sh){var s=shiftHours(sh)*60;return{reg:Math.min(total,s),ot:Math.max(0,total-s)}}
function otRate(sh){return settings.insuranceWage>0?settings.insuranceWage/30/shiftHours(sh):0}
function setRing(p,ot){var r=$('ringP');r.style.strokeDashoffset=615.75*(1-Math.max(0,Math.min(1,p)));r.classList.toggle('ot',!!ot)}
function paintSeg(seg,v){seg.querySelectorAll('button').forEach(function(b){b.classList.toggle('active',b.dataset.shift===v)})}
function paintShift(){paintSeg($('shiftSeg'),session?(session.shift||curShift):curShift)}
$('shiftSeg').addEventListener('click',function(ev){var b=ev.target.closest('button');if(!b)return;curShift=b.dataset.shift;if(session){session.shift=curShift;save(K.ses,session)}tick(true)});
function dayRate(){return settings.comprehensiveSalary>0?settings.comprehensiveSalary/30:0}
function uid(){return Date.now().toString(36)+Math.random().toString(36).slice(2,5)}
function saveAll(){save(K.s,settings);save(K.e,entries);save(K.h,holidays);save(K.r,restOverrides);save(K.a,absences)}

function applyStaticText(){
  document.documentElement.dir=t.dir;document.documentElement.lang=LANG;
  document.querySelectorAll('[data-i]').forEach(function(el){var v=t[el.dataset.i];if(typeof v==='string')el.innerHTML=v});
  $('stampMark').textContent='';
  $('staleMsg').textContent=t.staleMsg;
  ['setComprehensiveSalary','setInsuranceWage'].forEach(function(i){$(i).placeholder=t.placeholder});
  $('langArBtn').classList.toggle('active',LANG==='ar');$('langEnBtn').classList.toggle('active',LANG==='en');
  renderRestDayChips();renderHolidayList();renderRemindUI();
}

var tabs=document.querySelectorAll('.nav button');
tabs.forEach(function(btn){btn.addEventListener('click',function(){
  tabs.forEach(function(b){b.classList.remove('active')});btn.classList.add('active');
  document.querySelectorAll('.tab-page').forEach(function(p){p.classList.remove('active')});
  $('tab-'+btn.dataset.tab).classList.add('active');
  $('addEntryFab').style.display=btn.dataset.tab==='history'?'block':'none';
  if(btn.dataset.tab==='history')renderHistory();
  window.scrollTo(0,0);
})});

var lastMin=-1,timer=null;
function tick(force){
  var now=new Date(),x=hm12(now);
  $('liveClock').innerHTML=x.h+':'+pad(now.getSeconds())+'<span class="ampm">'+x.ap+'</span>';
  var mk=now.getHours()*60+now.getMinutes();
  if(force||mk!==lastMin){
    lastMin=mk;
    $('todayDate').textContent=t.weekdays[now.getDay()]+t.comma+now.getDate()+' '+t.months[now.getMonth()];
    updateStatus(now);checkReminders(now);
  }
}
function setPay(el,row,min,r){if(r>0){row.style.display='flex';el.textContent=fmtMoney(min/60*r*settings.multiplier)+' '+settings.currency}else row.style.display='none'}
function updateStatus(now){
  var st=$('statusLine'),btn=$('punchBtn'),card=$('todayCard');
  if(session&&session.clockIn){
    var start=new Date(session.clockIn),tot=(now-start)/60000,sh=session.shift||curShift,sp=split(tot,sh);setRing(tot/(shiftHours(sh)*60),sp.ot>0);paintShift();
    $('punchLabel').textContent=t.clockOut;
    if(sp.ot>0){st.className='status-line overtime';st.textContent=t.workingSinceOT(fmtTimeHM(start),fmtDur(tot));btn.classList.add('overtime');btn.classList.remove('out')}
    else{st.className='status-line working';st.textContent=t.workingSince(fmtTimeHM(start),fmtDur(tot));btn.classList.remove('overtime');btn.classList.add('out')}
    card.style.display='grid';$('todayIn').textContent=fmtTimeHM(start);
    $('todayRegular').textContent=fmtDur(sp.reg);$('todayOvertime').textContent=fmtDur(sp.ot);
    setPay($('todayPay'),$('todayPayRow'),sp.ot,otRate(sh));
    $('staleBanner').classList.toggle('show',tot>16*60);
  }else{
    btn.classList.remove('out','overtime');$('punchLabel').textContent=t.clockIn;paintShift();setRing(0,false);$('staleBanner').classList.remove('show');
    var key=dateKey(now),te=entries.filter(function(e){return e.date===key&&e.clockIn}).sort(function(a,b){return b.clockIn.localeCompare(a.clockIn)})[0];
    if(te){
      st.className='status-line';st.textContent=t.finishedToday(fmtTimeHM(new Date(te.clockOut)));card.style.display='grid';setRing(te.totalMin/(shiftHours(te.shift)*60),te.overtimeMin>0);
      $('todayIn').textContent=fmtTimeHM(new Date(te.clockIn));$('todayRegular').textContent=fmtDur(te.regularMin);$('todayOvertime').textContent=fmtDur(te.overtimeMin);
      setPay($('todayPay'),$('todayPayRow'),te.overtimeMin,otRate(te.shift));
    }else{st.className='status-line';st.textContent=t.notClockedIn;card.style.display='none'}
  }
}
function startTimer(){stopTimer();timer=setInterval(function(){tick(false)},1000)}
function stopTimer(){if(timer){clearInterval(timer);timer=null}}
document.addEventListener('visibilitychange',function(){if(document.hidden)stopTimer();else{tick(true);startTimer()}});

/* ---------- reminders ---------- */
function notify(msg){
  var b=$('remindBanner');$('remindMsg').textContent=msg;b.classList.add('show');
  try{if(navigator.vibrate)navigator.vibrate([200,100,200])}catch(e){}
  try{if('Notification' in window&&Notification.permission==='granted')new Notification(t.home,{body:msg})}catch(e){}
}
$('remindClose').addEventListener('click',function(){$('remindBanner').classList.remove('show')});
function checkReminders(now){
  var r=settings.remind;if(!r||!r.on)return;
  var key=dateKey(now),nm=now.getHours()*60+now.getMinutes();
  if(fired.date!==key)fired={date:key};
  function due(s){if(!s)return false;var p=s.split(':'),m=(+p[0])*60+(+p[1]);return nm>=m&&nm<m+30}
  var hasToday=entries.some(function(e){return e.date===key});
  if(!session&&!hasToday&&!fired.inDone&&due(r.inT)){fired.inDone=1;save(K.f,fired);notify(t.remindInMsg)}
  if(session&&!fired.outDone&&due(r.outT)){fired.outDone=1;save(K.f,fired);notify(t.remindOutMsg)}
}
function renderRemindUI(){
  var on=settings.remind.on,b=$('remindToggle');
  b.textContent=on?t.remindOn:t.remindOff;b.classList.toggle('active',on);
  $('remInT').value=settings.remind.inT;$('remOutT').value=settings.remind.outT;
}
$('remindToggle').addEventListener('click',function(){
  settings.remind.on=!settings.remind.on;save(K.s,settings);renderRemindUI();
  if(settings.remind.on&&'Notification' in window&&Notification.permission==='default'){
    try{Notification.requestPermission().then(function(p){if(p==='denied')alert(t.notifDenied)})}catch(e){}
  }else if(settings.remind.on&&(!('Notification' in window)||Notification.permission==='denied'))alert(t.notifDenied);
  fired={};tick(true);
});
['remInT','remOutT'].forEach(function(id){$(id).addEventListener('change',function(){
  settings.remind.inT=$('remInT').value||'09:00';settings.remind.outT=$('remOutT').value||'17:00';fired={};save(K.s,settings);tick(true)})});

/* ---------- punch ---------- */
$('punchBtn').addEventListener('click',function(){
  var stamp=$('stampMark');
  if(!session){session={clockIn:new Date().toISOString(),shift:curShift};save(K.ses,session);stamp.textContent=t.stampIn}
  else{
    var ci=new Date(session.clockIn),co=new Date(),tot=(co-ci)/60000,sh=session.shift||curShift,sp=split(tot,sh);
    entries.push({id:uid(),date:dateKey(ci),clockIn:ci.toISOString(),clockOut:co.toISOString(),totalMin:tot,regularMin:sp.reg,overtimeMin:sp.ot,shift:sh});
    save(K.e,entries);session=null;save(K.ses,null);stamp.textContent=t.stampOut;
  }
  $('remindBanner').classList.remove('show');
  stamp.classList.remove('show');void stamp.offsetWidth;stamp.classList.add('show');
  tick(true);
});
$('fixStaleBtn').addEventListener('click',function(){
  var s=session?new Date(session.clockIn):new Date(),n=new Date();
  openSheet({type:'work',stale:true,shift:session&&session.shift,date:dateKey(s),inTime:pad(s.getHours())+':'+pad(s.getMinutes()),outTime:pad(n.getHours())+':'+pad(n.getMinutes())});
});

/* ---------- month stats & chart ---------- */
function computeMonthStats(y,mi,monthEntries){
  var dim=new Date(y,mi+1,0).getDate(),today=new Date(),last=dim;
  if(y===today.getFullYear()&&mi===today.getMonth())last=today.getDate();
  else if(y>today.getFullYear()||(y===today.getFullYear()&&mi>today.getMonth()))last=0;
  function map(a){var o={};a.forEach(function(x){o[x.date]=1});return o}
  var ed=map(monthEntries),hm=map(holidays),rm=map(restOverrides),am=map(absences),rc=0,hc=0,ac=0;
  for(var d=1;d<=last;d++){
    var o=new Date(y,mi,d),k=dateKey(o);
    if(ed[k])continue;
    if(hm[k]){hc++;continue}
    if(rm[k]){rc++;continue}
    if(am[k]){ac++;continue}
    if(settings.restDays.indexOf(o.getDay())>-1){rc++;continue}
    ac++;
  }
  return{restCount:rc,holidayCount:hc,absenceCount:ac};
}
function chartHtml(y,mi,list){
  var dim=new Date(y,mi+1,0).getDate(),reg=[],ot=[],mx=(settings.standardHours||8)*60*1.25,i;
  for(i=0;i<=dim;i++){reg[i]=0;ot[i]=0}
  list.forEach(function(e){var d=parseInt(e.date.slice(8,10),10);if(d>=1&&d<=dim){reg[d]+=e.regularMin;ot[d]+=e.overtimeMin}});
  for(i=1;i<=dim;i++)mx=Math.max(mx,reg[i]+ot[i]);
  var W=300,H=100,top=6,bot=16,ph=H-top-bot,bw=W/dim,s='<svg viewBox="0 0 '+W+' '+H+'">';
  var sy=top+ph-((settings.standardHours||8)*60/mx)*ph;
  s+='<line x1="0" x2="'+W+'" y1="'+sy+'" y2="'+sy+'" stroke="#8A93A6" stroke-width=".6" stroke-dasharray="3 3"/>';
  for(i=1;i<=dim;i++){
    var x=(i-1)*bw+bw*.15,w=bw*.7,hr=reg[i]/mx*ph,ho=ot[i]/mx*ph;
    if(hr>0)s+='<rect x="'+x.toFixed(1)+'" y="'+(top+ph-hr).toFixed(1)+'" width="'+w.toFixed(1)+'" height="'+hr.toFixed(1)+'" rx="1.5" fill="#C8F25A"/>';
    if(ho>0)s+='<rect x="'+x.toFixed(1)+'" y="'+(top+ph-hr-ho).toFixed(1)+'" width="'+w.toFixed(1)+'" height="'+ho.toFixed(1)+'" rx="1.5" fill="#FF7A59"/>';
    if(i===1||i%5===0)s+='<text x="'+(x+w/2).toFixed(1)+'" y="'+(H-3)+'" font-size="7" text-anchor="middle" fill="#8A93A6">'+i+'</text>';
  }
  return '<div class="chart">'+s+'</svg><div class="lg"><span><i style="background:#C8F25A"></i>'+t.regular+'</span><span><i style="background:#FF7A59"></i>'+t.overtime+'</span></div></div>';
}

/* ---------- history ---------- */
function groupByMonth(){
  var g={};
  function p(dt,item){(g[dt.slice(0,7)]=g[dt.slice(0,7)]||[]).push(item)}
  entries.forEach(function(e){p(e.date,{kind:'work',date:e.date,data:e})});
  holidays.forEach(function(h){p(h.date,{kind:'holiday',date:h.date,data:h})});
  restOverrides.forEach(function(r){p(r.date,{kind:'rest',date:r.date,data:r})});
  absences.forEach(function(a){p(a.date,{kind:'absence',date:a.date,data:a})});
  return g;
}
function dayRowHtml(it){
  var d=new Date(it.date+'T00:00:00'),r='<div class="day-row" data-kind="'+it.kind+'" data-id="'+esc(it.data.id)+'"><div class="left"><div class="d">'+t.weekdays[d.getDay()]+t.comma+d.getDate()+(it.kind==='work'&&it.data.shift?'<span class="badge '+it.data.shift+'">'+shiftName(it.data.shift)+'</span>':'')+'</div>';
  if(it.kind==='work')r+='<div class="t mono">'+fmtTimeHM(new Date(it.data.clockIn))+' – '+fmtTimeHM(new Date(it.data.clockOut))+'</div></div><div class="right"><span class="r mono">'+fmtDur(it.data.regularMin)+'</span>'+(it.data.overtimeMin>0?'<span class="o mono">+'+fmtDur(it.data.overtimeMin)+'</span>':'')+'</div>';
  else r+='<div class="t">'+(it.kind==='holiday'?esc(it.data.name):it.kind==='rest'?t.restDaysCountLbl:t.absenceLbl)+'</div></div><div class="right"></div>';
  return r+'</div>';
}
function renderHistory(){
  var list=$('historyList');
  if(!entries.length&&!holidays.length&&!restOverrides.length&&!absences.length){list.innerHTML='<div class="empty">'+t.emptyHistory+'</div>';return}
  var g=groupByMonth(),html='';
  Object.keys(g).sort().reverse().forEach(function(mk){
    var items=g[mk].slice().sort(function(a,b){return b.date.localeCompare(a.date)});
    var y=parseInt(mk.slice(0,4),10),mo=parseInt(mk.slice(5,7),10)-1;
    var we=items.filter(function(i){return i.kind==='work'}).map(function(i){return i.data});
    var tOt=0,tReg=0,ud={};we.forEach(function(e){tOt+=e.overtimeMin;tReg+=e.regularMin;ud[e.date]=1});
    var wd=Object.keys(ud).length,ms=computeMonthStats(y,mo,we),dr=dayRate(),hr=settings.insuranceWage>0?1:0,otp=we.reduce(function(a,e){return a+e.overtimeMin/60*otRate(e.shift)*settings.multiplier},0),c=settings.currency;
    function cell(l,v,cls){return '<div class="stat-cell"><span>'+l+'</span><span class="v '+(cls||'')+' mono">'+v+'</span></div>'}
    html+='<div class="month-block"><div class="month-header"><span class="name">'+t.months[mo]+' '+y+'</span></div>'+chartHtml(y,mo,we)+'<div class="stat-grid">'
      +cell(t.workDaysLbl,wd)+cell(t.shiftMorning,we.filter(function(e){return e.shift==='morning'}).length)+cell(t.shiftEvening,we.filter(function(e){return e.shift==='evening'}).length)+cell(t.totalHoursLbl,fmtDur(tReg+tOt))+cell(t.overtime,fmtDur(tOt),'o')
      +(hr>0?cell(t.overtimePayLbl,fmtMoney(otp)+' '+c,'o'):'')
      +cell(t.restDaysCountLbl,ms.restCount)+cell(t.holidaysCountLbl,ms.holidayCount)+cell(t.absenceLbl,ms.absenceCount,'a')+'</div>';
    if(dr>0||hr>0){
      var wp=dr*wd,hp=dr*ms.holidayCount,rp=dr*ms.restCount,ad=dr*ms.absenceCount;
      html+='<div class="stat-grid">';
      if(dr>0)html+=cell(t.workDaysPayLbl,fmtMoney(wp)+' '+c)+cell(t.holidaysPayLbl,fmtMoney(hp)+' '+c)+cell(t.restPayLbl,fmtMoney(rp)+' '+c)+cell(t.absenceDeductionLbl,'-'+fmtMoney(ad)+' '+c,'a')+cell(t.totalSalaryDueLbl,fmtMoney(wp+hp+rp)+' '+c);
      html+=cell(t.grandTotalLbl,fmtMoney(wp+hp+rp+otp)+' '+c,'o')+'</div>';
    }
    [['work','workDaysSection'],['holiday','holidaysSection'],['rest','restSection'],['absence','absenceSection']].forEach(function(p){
      var sub=items.filter(function(i){return i.kind===p[0]});
      if(sub.length)html+='<div class="sub-heading">'+t[p[1]]+'</div>'+sub.map(dayRowHtml).join('');
    });
    html+='</div>';
  });
  list.innerHTML=html;
}
$('historyList').addEventListener('click',function(ev){
  var row=ev.target.closest&&ev.target.closest('.day-row');if(!row)return;
  var k=row.dataset.kind,id=row.dataset.id;
  function find(a){return a.filter(function(x){return x.id===id})[0]}
  function hmv(iso){var d=new Date(iso);return pad(d.getHours())+':'+pad(d.getMinutes())}
  if(k==='work'){var e=find(entries);if(e)openSheet({type:'work',shift:e.shift,date:e.date,entryId:e.id,inTime:hmv(e.clockIn),outTime:hmv(e.clockOut)})}
  else if(k==='holiday'){var h=find(holidays);if(h)openSheet({type:'holiday',date:h.date,holidayId:h.id,holidayName:h.name})}
  else if(k==='rest'){var r=find(restOverrides);if(r)openSheet({type:'rest',date:r.date,restId:r.id})}
  else{var a=find(absences);if(a)openSheet({type:'absence',date:a.date,absenceId:a.id})}
});
$('addEntryFab').addEventListener('click',function(){var n=new Date(),h=pad(n.getHours())+':'+pad(n.getMinutes());openSheet({type:'work',date:dateKey(n),inTime:h,outTime:h})});

/* ---------- edit sheet ---------- */
var ov=$('sheetOverlay'),editCtx=null,curType='work',sheetShift='morning';
function paintSheetShift(){paintSeg($('sheetShiftSeg'),sheetShift)}
$('sheetShiftSeg').addEventListener('click',function(ev){var b=ev.target.closest('button');if(b){sheetShift=b.dataset.shift;paintSheetShift()}});
$('editIn').addEventListener('change',function(){if(editCtx&&!editCtx.entryId&&!editCtx.stale){sheetShift=autoShift(parseInt(this.value,10)||0);paintSheetShift()}});
function setSheetType(ty){
  curType=ty;
  document.querySelectorAll('#dayTypeChips .chip').forEach(function(c){c.classList.toggle('active',c.dataset.type===ty)});
  $('workTimeFields').style.display=ty==='work'?'block':'none';
  $('holidayNameField').style.display=ty==='holiday'?'block':'none';
}
document.querySelectorAll('#dayTypeChips .chip').forEach(function(c){c.addEventListener('click',function(){setSheetType(c.dataset.type)})});
function openSheet(ctx){
  editCtx=ctx||{type:'work'};
  var isEdit=!!(editCtx.entryId||editCtx.holidayId||editCtx.restId||editCtx.absenceId),n=new Date(),hn=pad(n.getHours())+':'+pad(n.getMinutes());
  $('sheetTitle').textContent=isEdit?t.editDay:t.addDay;setSheetType(editCtx.type||'work');
  $('editDate').value=editCtx.date||dateKey(n);$('editIn').value=editCtx.inTime||hn;$('editOut').value=editCtx.outTime||hn;
  $('editHolidayName').value=editCtx.holidayName||'';$('deleteRow').style.display=isEdit?'flex':'none';
  sheetShift=editCtx.shift||autoShift(parseInt($('editIn').value,10)||0);paintSheetShift();ov.classList.add('show');
}
function closeSheet(){ov.classList.remove('show')}
$('sheetCancel').addEventListener('click',closeSheet);
ov.addEventListener('click',function(ev){if(ev.target===ov)closeSheet()});
function dropCtx(){
  if(!editCtx)return;
  if(editCtx.entryId)entries=entries.filter(function(x){return x.id!==editCtx.entryId});
  if(editCtx.holidayId)holidays=holidays.filter(function(x){return x.id!==editCtx.holidayId});
  if(editCtx.restId)restOverrides=restOverrides.filter(function(x){return x.id!==editCtx.restId});
  if(editCtx.absenceId)absences=absences.filter(function(x){return x.id!==editCtx.absenceId});
}
function refreshAll(){saveAll();closeSheet();renderHistory();renderHolidayList();tick(true)}
$('sheetSave').addEventListener('click',function(){
  var ds=$('editDate').value;if(!ds)return;
  var ty=curType,inS=$('editIn').value,outS=$('editOut').value,name=$('editHolidayName').value.trim();
  if(ty==='work'&&(!inS||!outS))return;
  if(ty==='holiday'&&!name)return;
  dropCtx();
  [['entries'],['holidays'],['restOverrides'],['absences']].length;
  var f=function(x){return x.date!==ds};
  entries=entries.filter(f);holidays=holidays.filter(f);restOverrides=restOverrides.filter(f);absences=absences.filter(f);
  if(ty==='work'){
    var ci=new Date(ds+'T'+inS+':00'),co=new Date(ds+'T'+outS+':00');
    if(co<=ci)co=new Date(co.getTime()+864e5);
    var tot=(co-ci)/60000,sp=split(tot,sheetShift);
    entries.push({id:uid(),date:dateKey(ci),clockIn:ci.toISOString(),clockOut:co.toISOString(),totalMin:tot,regularMin:sp.reg,overtimeMin:sp.ot,shift:sheetShift});
  }else if(ty==='holiday')holidays.push({id:uid(),date:ds,name:name});
  else if(ty==='rest')restOverrides.push({id:uid(),date:ds});
  else absences.push({id:uid(),date:ds});
  if(editCtx&&editCtx.stale&&session){session=null;save(K.ses,null)}
  refreshAll();
});
$('sheetDelete').addEventListener('click',function(){dropCtx();refreshAll()});

/* ---------- settings ---------- */
function loadSettingsUI(){
  $('setMorningHours').value=settings.morningHours;$('setEveningHours').value=settings.eveningHours;$('setComprehensiveSalary').value=settings.comprehensiveSalary||'';
  $('setInsuranceWage').value=settings.insuranceWage||'';$('setMultiplier').value=settings.multiplier;$('setCurrency').value=settings.currency;
}
['setMorningHours','setEveningHours','setComprehensiveSalary','setInsuranceWage','setMultiplier','setCurrency'].forEach(function(id){
  $(id).addEventListener('change',function(){
    settings.morningHours=parseFloat($('setMorningHours').value)||9;settings.eveningHours=parseFloat($('setEveningHours').value)||8;settings.standardHours=Math.min(settings.morningHours,settings.eveningHours);
    settings.comprehensiveSalary=parseFloat($('setComprehensiveSalary').value)||0;
    settings.insuranceWage=parseFloat($('setInsuranceWage').value)||0;
    settings.multiplier=parseFloat($('setMultiplier').value)||1.7;
    settings.currency=$('setCurrency').value||'جنيه';
    save(K.s,settings);tick(true);renderHistory();
  });
});
function renderRestDayChips(){
  var w=$('restDayChips');w.innerHTML='';
  t.weekdaysShort.forEach(function(n,i){
    var b=document.createElement('button');b.className='chip'+(settings.restDays.indexOf(i)>-1?' active':'');b.textContent=n;
    b.addEventListener('click',function(){var x=settings.restDays.indexOf(i);if(x>-1)settings.restDays.splice(x,1);else settings.restDays.push(i);save(K.s,settings);renderRestDayChips();renderHistory()});
    w.appendChild(b);
  });
}
function renderHolidayList(){
  var w=$('holidayList');
  if(!holidays.length){w.innerHTML='<div class="empty-mini">'+t.noHolidays+'</div>';return}
  w.innerHTML=holidays.slice().sort(function(a,b){return a.date.localeCompare(b.date)}).map(function(h){
    var d=new Date(h.date+'T00:00:00');
    return '<div class="holiday-row" data-id="'+esc(h.id)+'"><span>'+esc(h.name)+'</span><span class="hd mono">'+t.weekdays[d.getDay()]+t.comma+d.getDate()+' '+t.months[d.getMonth()]+'</span></div>';
  }).join('');
}
$('holidayList').addEventListener('click',function(ev){
  var row=ev.target.closest&&ev.target.closest('.holiday-row');if(!row)return;
  var h=holidays.filter(function(x){return x.id===row.dataset.id})[0];
  if(h)openSheet({type:'holiday',date:h.date,holidayId:h.id,holidayName:h.name});
});
$('addHolidayBtn').addEventListener('click',function(){openSheet({type:'holiday',date:dateKey(new Date())})});
function setLang(l){LANG=l;t=I18N[l];save(K.l,l);applyStaticText();renderHistory();tick(true)}
$('langArBtn').addEventListener('click',function(){setLang('ar')});
$('langEnBtn').addEventListener('click',function(){setLang('en')});

/* ---------- export ---------- */
function allRows(){
  var rows=[];
  entries.forEach(function(e){rows.push({d:e.date,k:'work',s:e.shift,i:e.clockIn,o:e.clockOut,r:e.regularMin,ot:e.overtimeMin})});
  holidays.forEach(function(h){rows.push({d:h.date,k:'holiday',n:h.name})});
  restOverrides.forEach(function(r){rows.push({d:r.date,k:'rest'})});
  absences.forEach(function(a){rows.push({d:a.date,k:'absence'})});
  return rows.sort(function(a,b){return a.d.localeCompare(b.d)});
}
function kindLabel(k){return k==='work'?t.workDayLabel:k==='holiday'?t.holidaysCountLbl:k==='rest'?t.restDaysCountLbl:t.absenceLbl}
function hh(m){return (Math.round(m/60*100)/100).toString()}
function csvCell(v){v=String(v==null?'':v);if(/^[=+\-@]/.test(v))v="'"+v;return '"'+v.replace(/"/g,'""')+'"'}
$('csvBtn').addEventListener('click',function(){
  var rows=allRows();if(!rows.length){alert(t.noData);return}
  var lines=[[t.date,t.dayTypeLabel,t.inTime,t.outTime,t.shiftLabel,t.regular+' ('+t.hoursUnit+')',t.overtime+' ('+t.hoursUnit+')',t.holidayNameLabel].map(csvCell).join(',')];
  rows.forEach(function(r){
    lines.push([r.d,kindLabel(r.k),r.i?fmtTimeHM(new Date(r.i)):'',r.o?fmtTimeHM(new Date(r.o)):'',shiftName(r.s),r.k==='work'?hh(r.r):'',r.k==='work'?hh(r.ot):'',r.n||''].map(csvCell).join(','));
  });
  var blob=new Blob(['\uFEFF'+lines.join('\r\n')],{type:'text/csv;charset=utf-8'});
  try{
    var a=document.createElement('a');a.href=URL.createObjectURL(blob);a.download='work-hours-'+dateKey(new Date())+'.csv';
    document.body.appendChild(a);a.click();setTimeout(function(){URL.revokeObjectURL(a.href);a.remove()},1000);
  }catch(e){alert(e.message)}
});
$('pdfBtn').addEventListener('click',function(){
  var g=groupByMonth(),keys=Object.keys(g).sort();if(!keys.length){alert(t.noData);return}
  var h='<h1>'+t.reportTitle+'</h1>';
  keys.forEach(function(mk){
    var y=parseInt(mk.slice(0,4),10),mo=parseInt(mk.slice(5,7),10)-1,tr=0,to=0,pay=0;
    var items=g[mk].sort(function(a,b){return a.date.localeCompare(b.date)});
    h+='<h2>'+t.months[mo]+' '+y+'</h2><table><tr><th>'+t.date+'</th><th>'+t.dayTypeLabel+'</th><th>'+t.inTime+' – '+t.outTime+'</th><th>'+t.regular+'</th><th>'+t.overtime+'</th></tr>';
    items.forEach(function(it){
      var d=new Date(it.date+'T00:00:00'),e=it.data;
      if(it.kind==='work'){tr+=e.regularMin;to+=e.overtimeMin;pay+=e.overtimeMin/60*otRate(e.shift)*settings.multiplier}
      h+='<tr><td>'+t.weekdays[d.getDay()]+t.comma+d.getDate()+'</td><td>'+kindLabel(it.kind)+(it.kind==='holiday'?' — '+esc(e.name):'')+'</td><td>'+(it.kind==='work'?fmtTimeHM(new Date(e.clockIn))+' – '+fmtTimeHM(new Date(e.clockOut))+(e.shift?' ('+shiftName(e.shift)+')':''):'')+'</td><td>'+(it.kind==='work'?fmtDur(e.regularMin):'')+'</td><td>'+(it.kind==='work'?fmtDur(e.overtimeMin):'')+'</td></tr>';
    });
    var r=settings.insuranceWage>0,tot='<b>'+t.totalHoursLbl+':</b> '+fmtDur(tr+to)+' &nbsp; <b>'+t.overtime+':</b> '+fmtDur(to);
    if(r>0)tot+=' &nbsp; <b>'+t.overtimePayLbl+':</b> '+fmtMoney(pay)+' '+esc(settings.currency);
    h+='</table><p style="font-size:12px">'+tot+'</p>';
  });
  $('printArea').innerHTML=h;
  setTimeout(function(){try{window.print()}catch(e){alert(t.pdfNote)}},50);
});

/* ---------- backup ---------- */
$('exportBtn').addEventListener('click',function(){
  var json=JSON.stringify({settings:settings,entries:entries,holidays:holidays,restOverrides:restOverrides,absences:absences}),area=$('backupArea'),btn=$('exportBtn'),orig=btn.textContent;
  area.value=json;
  function ok(){btn.textContent=t.copiedMsg;setTimeout(function(){btn.textContent=orig},1500)}
  if(navigator.clipboard&&navigator.clipboard.writeText)navigator.clipboard.writeText(json).then(ok).catch(function(){area.select()});
  else{area.select();try{document.execCommand('copy');ok()}catch(e){}}
});
$('importBtn').addEventListener('click',function(){
  var raw=$('backupArea').value;if(!raw||!raw.trim()){alert(t.importError);return}
  raw=raw.trim().replace(/[\u201C\u201D\u201F\u2033]/g,'"').replace(/[\u2018\u2019\u2032]/g,"'").replace(/\u00A0/g,' ');
  try{
    var d=JSON.parse(raw);if(!d||typeof d!=='object')throw new Error('bad');
    function a(x){return Array.isArray(x)?x.filter(validDate).map(function(i){if(!i.id)i.id=uid();return i}):null}
    if(d.settings&&typeof d.settings==='object'){settings=Object.assign({},DEF,d.settings);if(!Array.isArray(settings.restDays))settings.restDays=[5];settings.remind=Object.assign({},DEF.remind,settings.remind||{})}
    entries=a(d.entries)||entries;holidays=a(d.holidays)||holidays;restOverrides=a(d.restOverrides)||restOverrides;absences=a(d.absences)||absences;
    saveAll();loadSettingsUI();renderRestDayChips();renderHolidayList();renderRemindUI();renderHistory();tick(true);alert(t.importSuccess);
  }catch(e){alert(t.importError+'\n\n'+e.message)}
});
$('resetBtn').addEventListener('click',function(){
  if(!confirm(t.resetConfirm))return;
  try{Object.keys(K).forEach(function(k){if(k!=='l')localStorage.removeItem(K[k])})}catch(e){}
  settings=JSON.parse(JSON.stringify(DEF));session=null;entries=[];holidays=[];restOverrides=[];absences=[];fired={};
  loadSettingsUI();renderRestDayChips();renderHolidayList();renderRemindUI();renderHistory();tick(true);
});

saveAll();
loadSettingsUI();applyStaticText();tick(true);startTimer();
})();
</script>
</body>
</html>
