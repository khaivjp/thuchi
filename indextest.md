<!doctype html>
<html lang="vi">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
<meta name="theme-color" content="#15803d" />
<meta name="apple-mobile-web-app-capable" content="yes" />
<meta name="apple-mobile-web-app-status-bar-style" content="default" />
<meta name="apple-mobile-web-app-title" content="BeeRich" />
<link rel="apple-touch-icon" sizes="180x180" href="./beerich-icon.png" />
<link rel="icon" type="image/png" sizes="180x180" href="./beerich-icon.png" />
<title>KhaiRich Finance — Thu Chi cá nhân</title>
<style>
  :root{--blue:#15803d;--blue2:#16a34a;--ink:#14231a;--muted:#657568;--soft:#f0fdf4;--line:#e3eee6;--red:#f23843;--teal:#15803d;--shadow:0 8px 24px rgba(21,128,61,.08)}
  *{box-sizing:border-box}
  body{margin:0;background:#f7f8fb;color:var(--ink);font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Arial,sans-serif;font-size:16px;-webkit-font-smoothing:antialiased}
  button{font:inherit;cursor:pointer}button:focus-visible{outline:3px solid #9db7ff;outline-offset:3px}
  .app{width:min(100%,520px);min-height:100dvh;margin:0 auto;background:#fafbfe;position:relative;padding:calc(20px + env(safe-area-inset-top)) 20px calc(108px + env(safe-area-inset-bottom));overflow:hidden}
  .status{height:27px;display:flex;align-items:center;justify-content:space-between;padding:0 7px 8px;color:#10131a;font-weight:700;font-size:16px;letter-spacing:.1px}
  .status-right{display:flex;align-items:center;gap:8px;font-size:14px}.signal{font-size:17px;letter-spacing:-3px}.battery{border:1.5px solid #a6a9b1;border-radius:5px;padding:1px 4px;font-size:12px;position:relative}.battery:after{content:"";position:absolute;right:-4px;top:4px;width:3px;height:6px;background:#a6a9b1;border-radius:0 2px 2px 0}
  .brandbar{display:flex;align-items:center;justify-content:space-between;margin:10px 0 22px}
  .brand{display:flex;align-items:center;gap:8px;font-weight:450;font-size:26px;letter-spacing:-1.3px;color:#08090c}.brandmark{width:34px;height:34px;display:inline-grid;place-items:center;color:var(--blue);font-size:30px;line-height:1;font-weight:800}
  .brand-actions{display:flex;align-items:center;gap:17px}.sparkle{border:0;background:transparent;color:#1755f5;font-size:31px;line-height:1;padding:0}.close{border:0;background:transparent;font-size:31px;font-weight:300;line-height:1;color:#182033;padding:0 2px}
  .profile{display:flex;align-items:center;gap:12px;margin-bottom:26px}.avatar{width:62px;height:62px;flex:0 0 62px;border-radius:50%;display:grid;place-items:center;background:linear-gradient(140deg,#d1e2eb,#c5d1d0 46%,#f2d5bc);border:1px solid #e4e9f1;overflow:hidden;font-size:25px}.profile-copy{min-width:0;flex:1}.username{font-size:15px;color:#6d7b8d;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.rank{font-size:17px;font-weight:700;color:#4a5361;margin-top:5px}.wallet{border:0;border-radius:24px;padding:9px 16px;background:var(--blue);color:white;font-weight:650;font-size:14px;white-space:nowrap}
  .panel{background:#fff;border:1px solid #edf0f5;border-radius:25px;box-shadow:var(--shadow);padding:24px 24px 22px;position:relative}
  .panel-head{display:flex;justify-content:space-between;align-items:center;gap:10px}.eyebrow{font-size:19px;color:#515a68;display:flex;align-items:center;gap:8px}.chevron{display:inline-block;width:11px;height:11px;border-right:3px solid currentColor;border-bottom:3px solid currentColor;transform:rotate(45deg);margin-top:-6px}
  .month-control{display:flex;align-items:center;gap:6px;flex-shrink:0}.month-arrow{width:34px;height:36px;border:1px solid #e6ebf5;background:#f6f8ff;color:var(--blue);border-radius:11px;font-size:22px;line-height:1;display:grid;place-items:center}.month-btn{position:relative;display:flex;gap:8px;align-items:center;justify-content:center;background:var(--blue);color:white;border:0;border-radius:12px;padding:10px 12px;font-size:14px;font-weight:700;white-space:nowrap;overflow:hidden}.month-picker-overlay{position:absolute;inset:0;width:100%;height:100%;opacity:0;cursor:pointer}.calendar-icon{font-size:17px}
  .total{font-size:37px;letter-spacing:-1.2px;font-weight:750;margin:8px 0 3px;line-height:1.15}.trend{color:var(--teal);font-weight:600;font-size:16px;display:flex;align-items:center;gap:6px}.trend-arrow{font-size:20px}
  .rule{height:1px;background:#e4e7ec;margin:24px 0 22px}.weekdays,.days{display:grid;grid-template-columns:repeat(7,minmax(0,1fr));text-align:center}.weekdays{color:#667487;font-size:14px;font-weight:550;margin-bottom:14px}.days{row-gap:15px}.day{min-height:58px;position:relative;display:flex;align-items:center;flex-direction:column;border:0;background:transparent;border-radius:18px;padding:4px 0 2px;color:#151b2a;min-width:0}.day .number{font-weight:550;font-size:17px;line-height:23px}.day .amount{font-size:12px;color:var(--red);margin-top:3px;white-space:nowrap;letter-spacing:-.25px;line-height:1.1}.day .amount.income{color:var(--teal)}.day .amount.expense{color:var(--red)}.day.muted{color:#b4b7bd}.day.today{background:#f0f4fc}.day:active{background:#eaf0ff}.calendar-footer{border-top:1px solid #e6e9ef;margin-top:18px;padding-top:18px;display:flex;align-items:center;justify-content:space-between;gap:10px;color:#5d6673;font-size:15px}.outline-btn{border:1.5px solid var(--blue);color:var(--blue);background:white;border-radius:24px;padding:8px 17px;font-weight:600;white-space:nowrap}
  .dots{display:flex;justify-content:center;align-items:center;gap:12px;margin:16px auto 0;background:white;border:1px solid #edf0f5;border-radius:30px;width:max-content;padding:10px 17px;box-shadow:0 3px 14px rgba(20,40,80,.04)}.dot{border:0;background:#aab6c7;width:12px;height:12px;border-radius:50%;padding:0}.dot.active{width:34px;border-radius:12px;background:var(--blue)}
  .insight{border:1.5px solid var(--blue);border-radius:20px;padding:17px 20px;margin-top:74px;background:rgba(255,255,255,.45);font-size:16px;line-height:1.5}.insight-link{display:flex;align-items:center;gap:8px;color:var(--blue);font-weight:650;margin-top:12px;font-size:16px}.right-arrow{font-size:25px;font-weight:300;line-height:1}
  .bottom-nav{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:min(100%,520px);padding:19px 15px calc(17px + env(safe-area-inset-bottom));background:rgba(255,255,255,.97);backdrop-filter:blur(18px);border:2px solid #7686f5;border-bottom:0;border-radius:34px 34px 0 0;display:grid;grid-template-columns:repeat(2,1fr);gap:8px;z-index:10}.nav-item{border:0;background:transparent;border-radius:18px;min-height:76px;color:#121927;display:flex;flex-direction:column;justify-content:center;align-items:center;gap:6px;font-size:16px}.nav-item.active{background:var(--blue);color:white}.nav-icon{height:28px;display:flex;align-items:center;font-size:25px;line-height:1}.nav-label{font-weight:550}
  .assets-card{text-align:center;padding-top:30px}.assets-title{display:flex;justify-content:center;align-items:center;gap:10px;color:#5e6672;font-size:20px}.assets-value{font-size:35px;letter-spacing:-1px;font-weight:760;margin:12px 0 28px}.gauge{width:160px;height:80px;margin:0 auto 26px;position:relative;overflow:hidden}.gauge:before{content:"";position:absolute;width:150px;height:150px;left:5px;top:0;border:22px solid #e8edf9;border-bottom-color:transparent;border-radius:50%;transform:rotate(0deg)}.gauge:after{content:"";position:absolute;width:150px;height:150px;left:5px;top:0;border:22px solid #3567f7;border-bottom-color:transparent;border-radius:50%;clip-path:inset(0 0 50% 0)}.gauge span{position:absolute;left:0;right:0;bottom:5px;z-index:1;font-size:20px;font-weight:700}
  .asset-grid{display:grid;grid-template-columns:1fr 1fr;text-align:left;gap:23px 14px;margin-bottom:28px}.asset-item{min-width:0}.asset-name{color:#606a78;display:flex;gap:8px;align-items:center;font-size:16px;white-space:nowrap}.asset-name:before{content:"";width:4px;height:19px;border-radius:4px;background:var(--blue);flex:0 0 4px}.asset-item:nth-child(2) .asset-name:before{background:#6e96ff}.asset-item:nth-child(3) .asset-name:before{background:#4c75f9}.asset-item:nth-child(4) .asset-name:before{background:#a7bdff}.asset-item:nth-child(5) .asset-name:before{background:#b5c5ee}.asset-item:nth-child(6) .asset-name:before{background:#d6dff7}.asset-money{font-size:18px;font-weight:550;margin-top:5px;white-space:nowrap}.wide-btn{width:100%;border:1.5px solid var(--blue);color:var(--blue);background:#fff;border-radius:40px;padding:15px 12px;font-size:18px;font-weight:600;margin-bottom:17px}.promo{border-radius:24px;background:#eef3ff;text-align:left;padding:18px 17px;color:#1651dc}.promo-title{font-size:18px;font-weight:750;margin-bottom:9px}.promo-copy{font-size:15px;color:#717d90;line-height:1.5}.promo-link{color:#1751dc;font-size:15px;font-weight:650;text-align:right;margin-top:12px}
  .money-card{padding:24px;margin-bottom:16px;background:linear-gradient(145deg,#fff 0%,#f4f7ff 100%)}
  .month-stats{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin:0 0 17px}.month-stat{padding:13px 14px;border:1px solid #e9edf5;border-radius:15px;background:#fff;min-width:0}.month-stat-label{font-size:13px;color:#727d8c}.month-stat-value{font-size:18px;font-weight:750;margin-top:5px;overflow-wrap:anywhere}.month-stat.income .month-stat-value{color:var(--teal)}.month-stat.expense .month-stat-value{color:var(--red)}
  .history-panel{margin-top:16px}.history-heading{font-weight:750;font-size:18px;margin-bottom:10px}.history-empty{color:#778293;font-size:14px;line-height:1.5;padding:12px 0}.transaction-row{display:flex;align-items:center;gap:10px;padding:13px 0;border-bottom:1px solid var(--line)}.transaction-row:last-child{border-bottom:0}.tx-badge{flex:0 0 38px;width:38px;height:38px;border-radius:12px;display:grid;place-items:center;font-size:18px;font-weight:750;background:#eef3ff;color:var(--blue)}.tx-badge.income{background:#e8f8f4;color:var(--teal)}.tx-badge.expense{background:#fff0f1;color:var(--red)}.tx-info{min-width:0;flex:1}.tx-name{font-weight:650;overflow-wrap:anywhere}.tx-date{color:#7a8493;font-size:12px;margin-top:4px}.tx-side{text-align:right;flex-shrink:0}.tx-amount{font-weight:750;white-space:nowrap}.tx-amount.income{color:var(--teal)}.tx-amount.expense{color:var(--red)}.tx-delete{border:0;background:transparent;color:#8c96a5;padding:5px 0 0;font-size:12px;text-decoration:underline}
  .money-head{display:flex;align-items:center;justify-content:space-between;gap:12px;color:#596575;font-size:17px;font-weight:600}
  .visibility-btn{border:0;background:#edf2ff;color:#1550f5;border-radius:12px;width:40px;height:38px;font-size:20px;display:grid;place-items:center}
  .money-value{font-size:clamp(32px,8vw,40px);font-weight:800;letter-spacing:-1.1px;line-height:1.2;margin:14px 0 8px;overflow-wrap:anywhere}
  .money-note{font-size:13px;line-height:1.45;color:#7a8493;margin-bottom:18px}
  .money-actions{display:flex;align-items:center;gap:10px;flex-wrap:wrap}
  .assets-heading{display:flex;align-items:flex-start;justify-content:space-between;gap:12px;margin-bottom:18px}
  .assets-heading-title{font-size:21px;font-weight:750}
  .assets-heading-sub{color:#768191;font-size:13px;line-height:1.4;margin-top:5px}
  .tracked-assets{display:grid;grid-template-columns:1fr 1fr;gap:12px}
  .tracked-asset{display:flex;flex-direction:column;align-items:flex-start;text-align:left;min-width:0;min-height:135px;border:1px solid #e9edf5;border-radius:18px;background:#fbfcff;padding:16px;color:var(--ink)}
  .tracked-asset:active{background:#f0f4ff}
  .tracked-icon{width:37px;height:37px;border-radius:12px;background:#edf2ff;color:#1550f5;display:grid;place-items:center;font-size:21px;margin-bottom:13px}
  .tracked-label{font-size:14px;color:#626d7b;line-height:1.35}
  .tracked-value{font-size:clamp(16px,4vw,20px);font-weight:750;margin-top:7px;overflow-wrap:anywhere}
  .tracked-hint{font-size:12px;color:#8b95a3;margin-top:7px}
  .section-title{font-size:24px;font-weight:750;margin:5px 0 7px}.section-sub{color:#6a7585;font-size:15px;margin-bottom:20px}.mini-stat{border-radius:17px;background:#f2f5ff;padding:15px;margin-bottom:12px}.mini-stat-label{color:#687486;font-size:14px}.mini-stat-value{font-size:24px;font-weight:750;margin-top:5px}.saving-row{display:flex;align-items:center;gap:13px;padding:16px 0;border-bottom:1px solid var(--line)}.saving-icon{width:45px;height:45px;border-radius:15px;background:#edf2ff;display:grid;place-items:center;font-size:22px}.saving-detail{flex:1}.saving-name{font-weight:700}.saving-desc{color:#737e8d;font-size:14px;margin-top:4px}.saving-value{font-weight:700;text-align:right;white-space:nowrap}
  .modal-backdrop{position:fixed;inset:0;background:rgba(12,20,37,.4);display:none;align-items:flex-end;justify-content:center;z-index:30;padding:15px}.modal-backdrop.show{display:flex}.modal{width:min(100%,480px);background:white;border-radius:25px;padding:23px;box-shadow:0 20px 70px rgba(0,0,0,.2)}.modal-head{display:flex;justify-content:space-between;align-items:center;font-size:21px;font-weight:750;margin-bottom:18px}.modal-close{border:0;background:#f1f3f8;border-radius:50%;height:34px;width:34px;font-size:23px}.field{display:block;margin:14px 0;color:#525d6c;font-size:14px}.field input,.field select{display:block;width:100%;margin-top:7px;border:1px solid #dfe4ee;border-radius:12px;padding:13px;font:inherit;color:var(--ink);background:white}.submit-btn{width:100%;margin-top:12px;border:0;background:var(--blue);border-radius:14px;color:white;font-weight:700;padding:14px}
  @media(min-width:600px){body{padding:24px 0}.app{border-radius:28px;min-height:calc(100dvh - 48px);box-shadow:0 15px 60px rgba(30,50,80,.1)}.bottom-nav{bottom:24px;border-radius:30px;width:min(calc(100% - 40px),480px);border-bottom:2px solid #7686f5}.modal-backdrop{align-items:center}}
  @media(max-width:380px){.app{padding-left:14px;padding-right:14px}.panel{padding:20px 16px}.total{font-size:32px}.day .amount{font-size:11px}.calendar-footer{font-size:13px}.outline-btn{padding:7px 12px;font-size:13px}.brand{font-size:24px}.profile{gap:9px}.avatar{width:54px;height:54px;flex-basis:54px}.username{font-size:13px}.rank{font-size:15px}.wallet{padding:8px 12px}.eyebrow{font-size:15px}.panel-head{gap:5px}.month-control{gap:2px}.month-arrow{width:25px;height:32px;font-size:19px}.month-btn{font-size:11px;padding:8px 5px;gap:4px}.calendar-icon{font-size:14px}.asset-name{font-size:14px}.asset-money{font-size:16px}.month-stat-value{font-size:15px}}

  /* BeeRich Finance: gọn gàng, xanh lá và đồng bộ Git độc lập */
  body{background:#f0fdf4}
  .app{background:#f7fdf8}
  .panel{border-color:#e2f0e6}
  .money-card{background:linear-gradient(145deg,#ffffff 0%,#f0fdf4 100%)}
  .month-arrow{background:#f0fdf4;border-color:#bbf7d0}
  .day.today{background:#dcfce7}
  .day:active{background:#bbf7d0}
  .dots{border-color:#dcfce7}
  .bottom-nav{border-color:#86efac}
  .gauge:before{border-color:#dcfce7;border-bottom-color:transparent}
  .gauge:after{border-color:#16a34a;border-bottom-color:transparent}
  .asset-item:nth-child(2) .asset-name:before,.asset-item:nth-child(3) .asset-name:before,.asset-item:nth-child(4) .asset-name:before,.asset-item:nth-child(5) .asset-name:before,.asset-item:nth-child(6) .asset-name:before{background:#86efac}
  .promo{background:#dcfce7;color:#166534}
  .tx-badge{background:#dcfce7}
  .tx-badge.income{background:#dcfce7;color:#166534}
  .nav-item.active{background:#15803d}
  .git-wallet{background:#166534;display:inline-flex;align-items:center;gap:6px}
  .git-wallet .git-dot{width:7px;height:7px;border-radius:50%;background:#bbf7d0;display:inline-block}
  .git-wallet[data-state="ok"] .git-dot{background:#86efac}
  .git-wallet[data-state="syncing"] .git-dot{background:#facc15}
  .git-wallet[data-state="error"] .git-dot{background:#fda4af}
  .brandbar-actions{display:flex;align-items:center;gap:7px}
  .git-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:12px}
  .git-action{border:1px solid #bbf7d0;background:#f0fdf4;color:#166534;border-radius:12px;padding:11px 9px;font-size:13px;font-weight:750}
  .git-action.primary{background:#15803d;color:#fff;border-color:#15803d}
  .git-status-line{font-size:12px;color:#166534;background:#f0fdf4;border:1px solid #dcfce7;padding:10px 12px;border-radius:12px;line-height:1.45;margin-top:10px;overflow-wrap:anywhere}
  .git-warning{font-size:11px;line-height:1.45;color:#64748b;margin-top:10px}
  .git-toggle{display:flex;gap:9px;align-items:flex-start;font-size:13px;line-height:1.4;color:#334155;margin-top:12px}
  .git-toggle input{margin-top:2px;accent-color:#15803d}
  .field input:focus,.field select:focus{outline:2px solid #86efac;border-color:#16a34a}
  @media(max-width:390px){.brandbar-actions{gap:5px}.git-wallet{padding:8px 10px;font-size:12px}.brandbar .wallet{padding:8px 11px;font-size:12px}}
</style>
</head>
<body>
<div class="app">
  <header class="brandbar"><div class="brand"><span class="brandmark">₫</span><span>KhaiRich</span></div><div class="brandbar-actions"><button class="wallet git-wallet" id="gitSyncBtn" data-state="idle" onclick="openGitModal()" title="Cấu hình đồng bộ Git"><span class="git-dot"></span><span id="gitSyncBtnText">Git Sync</span></button><button class="wallet" onclick="openModal('transaction')">＋ Giao dịch</button></div></header>
  <main id="mainContent"></main>
</div>
<nav class="bottom-nav" aria-label="Điều hướng chính">
  <button class="nav-item active" data-tab="overview" onclick="setTab('overview')"><span class="nav-icon">▦＋</span><span class="nav-label">Tổng quan</span></button>
  <button class="nav-item" data-tab="expense" onclick="setTab('expense')"><span class="nav-icon">💸</span><span class="nav-label">Thu chi</span></button>
</nav>

<div class="modal-backdrop" id="modalBackdrop" onclick="if(event.target===this)closeModal()"><div class="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle"><div class="modal-head"><span id="modalTitle">Tạo giao dịch</span><button class="modal-close" onclick="closeModal()" aria-label="Đóng">×</button></div><form id="transactionForm"><label class="field">Tên giao dịch<input id="txName" placeholder="Ví dụ: Ăn trưa" required /></label><label class="field">Số tiền (VNĐ)<input id="txAmount" type="number" min="1" placeholder="100000" required /></label><label class="field">Ngày giao dịch<input id="txDate" type="date" required /></label><label class="field">Loại giao dịch<select id="txType"><option value="expense">Chi tiêu</option><option value="saving">Dành dụm</option></select></label><button class="submit-btn" type="submit">Lưu giao dịch</button></form></div></div>

<div class="modal-backdrop" id="gitModalBackdrop" onclick="if(event.target===this)closeGitModal()"><div class="modal" role="dialog" aria-modal="true" aria-labelledby="gitModalTitle"><div class="modal-head"><span id="gitModalTitle">Đồng bộ BeeRich qua GitHub</span><button class="modal-close" onclick="closeGitModal()" aria-label="Đóng">×</button></div>
<form id="gitConfigForm">
<label class="field">GitHub Personal Access Token<input id="gitTokenInput" type="password" autocomplete="off" placeholder="github_pat_…" /></label>
<label class="field">Repository (owner/repo)<input id="gitRepoInput" placeholder="VD: username/khailife" required /></label>
<label class="field">Branch (để trống = mặc định)<input id="gitBranchInput" placeholder="main" /></label>
<label class="field">Đường dẫn file dữ liệu trên GitHub<input id="gitPathInput" value="beerich-finance-data.json" required /></label>
<label class="git-toggle"><input type="checkbox" id="gitAutoSyncInput" checked /><span><b>Tự động đồng bộ</b><br />Tự đẩy dữ liệu sau khi thêm/xóa giao dịch hoặc cập nhật tài sản; tự tải dữ liệu mới nhất khi mở trang.</span></label>
<div id="gitSyncStatus" class="git-status-line" role="status">Chưa cấu hình GitHub. Hãy nhập Token và Repository.</div>
<div class="git-grid"><button class="git-action primary" type="submit">Lưu cấu hình & đẩy lên Git</button><button class="git-action" type="button" onclick="gitPullData(true)">Tải từ Git về</button><button class="git-action" type="button" onclick="gitPushData(true)">Đẩy lên Git</button><button class="git-action" type="button" onclick="disconnectGitConfig()">Ngắt kết nối</button></div>
<p class="git-warning">Dùng GitHub Fine-grained token, chỉ cấp quyền Contents: Read and write cho đúng repository. Token được lưu trong localStorage của trình duyệt này; không chia sẻ file dữ liệu chứa token và không dùng token có quyền rộng không cần thiết.</p>
<div style="display:flex;justify-content:flex-end;margin-top:12px"><button class="outline-btn" type="button" onclick="closeGitModal()">Đóng</button></div>
</form></div></div>

<script>
const STORAGE_KEY = 'beerich-personal-dashboard-v2';
const defaults = { currentMoney: 1570349, savings: 0, gold: 14850000, hideCurrentMoney: false, transactions: [] };
let finances = loadFinances();
let activeTab = 'overview';
const startupDate = new Date();
let year = startupDate.getFullYear(), month = startupDate.getMonth(), selectedDay = startupDate.getDate(), modalKind = 'transaction';
const monthNames = ['Tháng 1','Tháng 2','Tháng 3','Tháng 4','Tháng 5','Tháng 6','Tháng 7','Tháng 8','Tháng 9','Tháng 10','Tháng 11','Tháng 12'];

function loadFinances(){
  const safeDefaults = () => ({...defaults, transactions: []});
  try {
    const saved = JSON.parse(localStorage.getItem(STORAGE_KEY) || 'null');
    const data = saved && typeof saved === 'object' ? {...defaults, ...saved} : safeDefaults();
    if (!Array.isArray(data.transactions)) data.transactions = [];
    data.transactions = data.transactions.filter(t => t && typeof t === 'object' && t.date && Number.isFinite(Number(t.amount)) && (t.type === 'income' || t.type === 'expense'));
    data.currentMoney = Number(data.currentMoney) || 0;
    data.savings = Number(data.savings) || 0;
    data.gold = Number(data.gold) || 0;
    data.hideCurrentMoney = Boolean(data.hideCurrentMoney);

    // Chuyển dữ liệu Thu–Chi đời cũ sang BeeRich đúng một lần nếu BeeRich chưa có giao dịch.
    const migrationKey = 'beerich_legacy_finance_migration_v1';
    if (!localStorage.getItem(migrationKey)) {
      if (!data.transactions.length) {
        let legacy = null;
        try { legacy = JSON.parse(localStorage.getItem('lifesync_minimal_v4') || 'null'); } catch {}
        const state = legacy && typeof legacy === 'object' ? legacy : null;
        const imported = [];
        const toDate = (item, monthKey) => {
          const source = item && (item.createdAt || item.dateTime);
          if (source) { const d = new Date(source); if (!Number.isNaN(d.getTime())) return dateKey(d.getFullYear(), d.getMonth(), d.getDate()); }
          const match = String(item && item.timeText || '').match(/(\d{2})\/(\d{2})\/(\d{4})/);
          if (match) return `${match[3]}-${match[2]}-${match[1]}`;
          if (/^\d{4}-\d{2}$/.test(monthKey || '')) return `${monthKey}-01`;
          const d = new Date(); return dateKey(d.getFullYear(), d.getMonth(), d.getDate());
        };
        const addItems = (items, monthKey) => (Array.isArray(items) ? items : []).forEach((item, index) => {
          const amount = Number(item && item.amount); if (!Number.isFinite(amount) || amount <= 0) return;
          const date = toDate(item, monthKey);
          const parsed = Date.parse(item && (item.createdAt || item.dateTime) || `${date}T12:00:00`);
          imported.push({id:`legacy-${monthKey || 'all'}-${String(item && item.id != null ? item.id : index)}`,name:String(item && (item.desc || item.name) || 'Khoản thu/chi').slice(0,100),amount,date,type:item && item.type === 'income' ? 'income':'expense',createdAt:Number.isFinite(parsed)?parsed:Date.now(),balanceApplied:false,legacyImported:true});
        });
        if (state && state.financeMonths && typeof state.financeMonths === 'object') {
          Object.entries(state.financeMonths).forEach(([mk, monthData]) => addItems(monthData && monthData.items, mk));
        }
        if (!imported.length && state) addItems(state.finance, state.financeCurrentMonth || '');
        if (imported.length) data.transactions = imported;
      }
      try { localStorage.setItem(migrationKey, '1'); } catch {}
    }
    try { localStorage.setItem(STORAGE_KEY, JSON.stringify(data)); } catch {}
    return data;
  } catch(e) { return safeDefaults(); }
}
function persistFinances(){
  try { localStorage.setItem(STORAGE_KEY, JSON.stringify(finances)); } catch(e) { /* Runs without persistence if browser storage is disabled. */ }
  if (!gitPullApplying) scheduleBeerichGitPush('Cập nhật dữ liệu BeeRich');
}
function formatVND(n){ return new Intl.NumberFormat('vi-VN', {maximumFractionDigits:0}).format(Number(n)||0) + ' đ'; }
function formatCompact(n){
  const value = Math.abs(Number(n)||0);
  if (value >= 1000000) return (value/1000000).toLocaleString('vi-VN',{maximumFractionDigits:1})+'tr';
  if (value >= 1000) return Math.round(value/1000).toLocaleString('vi-VN')+'K';
  return formatVND(value).replace(/\sđ$/, '');
}
function signedAmount(tx){ return `${tx.type === 'income' ? '+' : '−'}${formatVND(tx.amount)}`; }
function signedTotal(n, sign){ return (Number(n)>0?sign:'') + formatVND(n); }
function amountDisplay(n){ return finances.hideCurrentMoney ? '••••••••' : formatVND(n); }
function dateKey(y, m, d){ return `${y}-${String(m+1).padStart(2,'0')}-${String(d).padStart(2,'0')}`; }
function parseDateKey(key){ const [y,m,d] = String(key).split('-').map(Number); return new Date(y, m-1, d); }
function currentMonthTransactions(){ const prefix = `${year}-${String(month+1).padStart(2,'0')}-`; return finances.transactions.filter(t => t.date.startsWith(prefix)); }
function transactionsForDate(key){ return finances.transactions.filter(t => t.date === key).sort((a,b)=>(b.createdAt||0)-(a.createdAt||0)); }
function monthTotals(items=currentMonthTransactions()){
  return items.reduce((tot,t)=>{ if(t.type==='income') tot.income += Number(t.amount)||0; else tot.expense += Number(t.amount)||0; return tot; },{income:0,expense:0});
}
function toggleBalanceVisibility(){
  finances.hideCurrentMoney = !finances.hideCurrentMoney; persistFinances();
  const value=document.getElementById('currentMoneyValue'), eye=document.getElementById('balanceEye');
  if(value) value.textContent=amountDisplay(finances.currentMoney);
  if(eye){ eye.textContent=finances.hideCurrentMoney?'◉̸':'◉'; eye.setAttribute('aria-label',finances.hideCurrentMoney?'Hiện số dư':'Ẩn số dư'); }
}
function setTab(tab){
  activeTab=tab;
  document.querySelectorAll('.nav-item').forEach(b=>b.classList.toggle('active',b.dataset.tab===tab));
  document.getElementById('mainContent').innerHTML=tab==='overview'?overviewHTML():expenseHTML();
}
function overviewHTML(){
  return `<section class="panel money-card"><div class="money-head"><span>Số tiền tôi đang có</span><button class="visibility-btn" type="button" onclick="toggleBalanceVisibility()" aria-label="Ẩn số dư" title="Ẩn/hiện số dư"><span id="balanceEye">${finances.hideCurrentMoney?'◉̸':'◉'}</span></button></div><div class="money-value" id="currentMoneyValue">${amountDisplay(finances.currentMoney)}</div><div class="money-note">Mỗi khoản thu sẽ cộng, mỗi khoản chi sẽ trừ số dư này.</div><div class="money-actions"><button class="outline-btn" onclick="openModal('balance')">Cập nhật số tiền</button><button class="outline-btn" onclick="openModal('transaction','income')">＋ Thêm khoản thu</button><button class="outline-btn" onclick="openModal('transaction','expense')">− Thêm khoản chi</button></div></section><section class="panel assets-card"><div class="assets-heading"><div><div class="assets-heading-title">Tài sản của tôi</div><div class="assets-heading-sub">Theo dõi riêng tiền tiết kiệm và vàng; không cộng vào số dư đang có.</div></div></div><div class="tracked-assets"><button class="tracked-asset" type="button" onclick="openModal('savings')"><span class="tracked-icon">▣</span><span class="tracked-label">Tiền tiết kiệm của tôi</span><strong class="tracked-value">${formatVND(finances.savings)}</strong><span class="tracked-hint">Chạm để chỉnh sửa　›</span></button><button class="tracked-asset" type="button" onclick="openModal('gold')"><span class="tracked-icon">◈</span><span class="tracked-label">Vàng</span><strong class="tracked-value">${formatVND(finances.gold)}</strong><span class="tracked-hint">Chạm để chỉnh sửa　›</span></button></div></section><section class="panel history-panel"><div class="history-heading">Giao dịch gần đây</div>${recentTransactionsHTML(5)}</section>`;
}
function recentTransactionsHTML(limit){
  const items=[...finances.transactions].sort((a,b)=>(b.createdAt||0)-(a.createdAt||0)).slice(0,limit);
  if(!items.length) return '<div class="history-empty">Chưa có giao dịch nào. Hãy thêm khoản thu hoặc chi để bắt đầu theo dõi.</div>';
  return items.map(t=>transactionRowHTML(t)).join('');
}
function transactionRowHTML(t){
  const income=t.type==='income';
  return `<div class="transaction-row"><span class="tx-badge ${income?'income':'expense'}">${income?'＋':'−'}</span><div class="tx-info"><div class="tx-name">${escapeHTML(t.name)}</div><div class="tx-date">${formatDate(t.date)} · ${income?'Khoản thu':'Khoản chi'}</div></div><div class="tx-side"><div class="tx-amount ${income?'income':'expense'}">${income?'+':'−'}${formatVND(t.amount)}</div><button class="tx-delete" onclick="deleteTransaction('${t.id}')">Xóa</button></div></div>`;
}
function escapeHTML(value){ return String(value??'').replace(/[&<>"']/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c])); }
function formatDate(key){ const [y,m,d]=key.split('-'); return `${d}/${m}/${y}`; }
function expenseHTML(){
  const first = new Date(year,month,1).getDay(), mondayOffset=(first+6)%7;
  const count = new Date(year,month+1,0).getDate(), prevCount = new Date(year,month,0).getDate();
  const cells=[];
  for(let i=0;i<mondayOffset;i++) cells.push({d:prevCount-mondayOffset+1+i,offset:-1});
  for(let d=1;d<=count;d++) cells.push({d,offset:0});
  let next=1; while(cells.length<42) cells.push({d:next++,offset:1});
  const dayNames=['Thứ 2','Thứ 3','Thứ 4','Thứ 5','Thứ 6','Thứ 7','CN'];
  const monthTx=currentMonthTransactions(), totals=monthTotals(monthTx);
  const selectedKey=selectedDay?dateKey(year,month,selectedDay):null;
  const selectedTx=selectedKey?transactionsForDate(selectedKey):[];
  const cellsHTML=cells.map(c=>{
    const current=c.offset===0, key=current?dateKey(year,month,c.d):null;
    const dayTx=current?transactionsForDate(key):[]; const t=monthTotals(dayTx);
    const selected=current&&c.d===selectedDay;
    return `<button class="day ${current?'':'muted'} ${selected?'today':''}" ${current?`onclick="selectDay(${c.d})"`: 'disabled'} aria-label="${current?`${c.d} ${monthNames[month]} ${year}`:'Ngày ngoài tháng hiện tại'}"><span class="number">${c.d}</span>${t.income?`<span class="amount income">+${formatCompact(t.income)}</span>`:''}${t.expense?`<span class="amount expense">−${formatCompact(t.expense)}</span>`:''}</button>`;
  }).join('');
  const selectedText=selectedKey?`Giao dịch ngày ${formatDate(selectedKey)}`:'Chọn ngày để xem giao dịch';
  const selectedDetails=selectedKey?(selectedTx.length?selectedTx.map(transactionRowHTML).join(''):'<div class="history-empty">Chưa có giao dịch trong ngày này.</div>'):'<div class="history-empty">Chạm vào một ngày trên lịch để xem các khoản thu và chi.</div>';
  return `<section class="panel"><div class="panel-head"><div class="eyebrow">Lịch thu chi</div><div class="month-control"><button class="month-arrow" type="button" onclick="changeMonth(-1)" aria-label="Tháng trước">‹</button><label class="month-btn"><span class="calendar-icon">▦</span><span>${monthNames[month]} ${year}</span><input class="month-picker-overlay" type="month" aria-label="Chọn tháng và năm" value="${year}-${String(month+1).padStart(2,'0')}" onchange="pickMonth(this.value)"></label><button class="month-arrow" type="button" onclick="changeMonth(1)" aria-label="Tháng sau">›</button></div></div><div class="total">${signedTotal(totals.expense,'−')}</div><div class="trend"><span class="trend-arrow">↗</span> Tổng chi trong ${monthNames[month].toLowerCase()} ${year}</div><div class="month-stats"><div class="month-stat income"><div class="month-stat-label">Tổng thu</div><div class="month-stat-value">${signedTotal(totals.income,'+')}</div></div><div class="month-stat expense"><div class="month-stat-label">Tổng chi</div><div class="month-stat-value">${signedTotal(totals.expense,'−')}</div></div></div><div class="rule"></div><div class="weekdays">${dayNames.map(d=>`<div>${d}</div>`).join('')}</div><div class="days">${cellsHTML}</div><div class="calendar-footer"><span id="calendarFooterText">${selectedKey?`Đang chọn ngày ${selectedDay}`:'Chọn một ngày để xem thu chi'}</span><button class="outline-btn" onclick="openModal('transaction','expense')">＋ Giao dịch</button></div></section><section class="panel history-panel"><div class="history-heading">${selectedText}</div>${selectedDetails}</section><section class="panel history-panel"><div class="history-heading">Giao dịch trong ${monthNames[month].toLowerCase()} ${year}</div>${monthTx.length?[...monthTx].sort((a,b)=>b.date.localeCompare(a.date)||(b.createdAt||0)-(a.createdAt||0)).map(transactionRowHTML).join(''):'<div class="history-empty">Tháng này chưa có giao dịch. Nhấn “＋ Giao dịch” để thêm khoản thu hoặc chi.</div>'}</section>`;
}
function changeMonth(delta){
  const date=new Date(year,month+delta,1); year=date.getFullYear(); month=date.getMonth(); selectedDay=null; setTab('expense');
}
function pickMonth(value){ if(!value)return; const [y,m]=value.split('-').map(Number); if(!y||!m)return; year=y; month=m-1; selectedDay=null; setTab('expense'); }
function selectDay(day){ selectedDay=day; setTab('expense'); }
function openModal(kind, initialType='expense'){
  modalKind=kind;
  const titles={balance:'Cập nhật số tiền hiện có',savings:'Cập nhật tiền tiết kiệm',gold:'Cập nhật giá trị vàng',transaction:initialType==='income'?'Thêm khoản thu':'Thêm khoản chi'};
  document.getElementById('modalTitle').textContent=titles[kind]||'Cập nhật thông tin';
  const form=document.getElementById('transactionForm');
  if(kind==='balance'||kind==='savings'||kind==='gold'){
    const key=kind==='balance'?'currentMoney':kind;
    form.innerHTML=`<label class="field">${kind==='balance'?'Số tiền hiện có (VNĐ)':kind==='savings'?'Tiền tiết kiệm (VNĐ)':'Giá trị vàng (VNĐ)'}<input id="txAmount" type="number" min="0" step="1" value="${Number(finances[key])||0}" required /></label><button class="submit-btn" type="submit">Lưu thay đổi</button>`;
  }else{
    const presetDate=selectedDay?dateKey(year,month,selectedDay):dateKey(year,month,1);
    form.innerHTML=`<label class="field">Tên giao dịch<input id="txName" maxlength="100" placeholder="Ví dụ: Lương, ăn trưa, tiền làm thêm" required /></label><label class="field">Số tiền (VNĐ)<input id="txAmount" type="number" min="1" step="1" placeholder="100000" required /></label><label class="field">Ngày giao dịch<input id="txDate" type="date" value="${presetDate}" required /></label><label class="field">Loại giao dịch<select id="txType"><option value="expense" ${initialType==='expense'?'selected':''}>Chi tiêu — trừ số tiền</option><option value="income" ${initialType==='income'?'selected':''}>Thu nhập — cộng số tiền</option></select></label><button class="submit-btn" type="submit">Lưu giao dịch và cập nhật số dư</button>`;
    document.getElementById('txType').addEventListener('change',e=>{document.getElementById('modalTitle').textContent=e.target.value==='income'?'Thêm khoản thu':'Thêm khoản chi';});
  }
  document.getElementById('modalBackdrop').classList.add('show'); setTimeout(()=>form.querySelector('input')?.focus(),60);
}
function closeModal(){ document.getElementById('modalBackdrop').classList.remove('show'); }
function deleteTransaction(id){
  const tx=finances.transactions.find(t=>t.id===id); if(!tx)return;
  if(!confirm(`Xóa giao dịch “${tx.name}” (${signedAmount(tx)})? Số dư sẽ được hoàn lại tương ứng.`))return;
  if(tx.balanceApplied!==false){ finances.currentMoney += tx.type==='income' ? -Number(tx.amount) : Number(tx.amount); }
  finances.transactions=finances.transactions.filter(t=>t.id!==id); persistFinances(); setTab(activeTab);
}
document.getElementById('transactionForm').addEventListener('submit',e=>{
  e.preventDefault();
  const amount=Number(document.getElementById('txAmount')?.value);
  if(!Number.isFinite(amount)||amount<0)return;
  if(['balance','savings','gold'].includes(modalKind)){
    const key=modalKind==='balance'?'currentMoney':modalKind; finances[key]=amount; persistFinances(); closeModal(); setTab('overview'); return;
  }
  const name=document.getElementById('txName')?.value.trim();
  const date=document.getElementById('txDate')?.value;
  const type=document.getElementById('txType')?.value==='income'?'income':'expense';
  if(!name||!date||amount<=0)return;
  const tx={id:(window.crypto&&crypto.randomUUID)?crypto.randomUUID():`${Date.now()}-${Math.random().toString(36).slice(2,9)}`,name,amount,date,type,createdAt:Date.now(),balanceApplied:true};
  finances.transactions.push(tx);
  finances.currentMoney += type==='income'?amount:-amount;
  persistFinances();
  const [y,m,d]=date.split('-').map(Number); year=y; month=m-1; selectedDay=d;
  closeModal(); setTab(activeTab==='overview'?'overview':'expense');
});


const BEERICH_GIT_CONFIG_KEY = 'beerich_finance_git_config_v1';
let beerichGitPushTimer = null;
let beerichGitBusy = false;
let gitPullApplying = false;

function detectBeerichGitRepo(){
  const host = window.location.hostname;
  const parts = window.location.pathname.split('/').filter(Boolean);
  if (host.endsWith('.github.io')) {
    const owner = host.replace('.github.io','');
    return `${owner}/${parts[0] || `${owner}.github.io`}`;
  }
  return '';
}
function getBeerichGitConfig(){
  try {
    const saved = JSON.parse(localStorage.getItem(BEERICH_GIT_CONFIG_KEY) || 'null');
    if (saved && typeof saved === 'object') return {...saved, path:saved.path || 'beerich-finance-data.json'};
  } catch {}
  return {token:'', repo:detectBeerichGitRepo(), branch:'', path:'beerich-finance-data.json', autoSync:true};
}
function beerichGitConfigured(){ const c=getBeerichGitConfig(); return Boolean(c.token && c.repo && c.repo.includes('/')); }
function beerichGitMessage(text, kind='idle'){
  const status=document.getElementById('gitSyncStatus');
  const button=document.getElementById('gitSyncBtn');
  const label=document.getElementById('gitSyncBtnText');
  if(status) status.textContent=text;
  if(button) button.dataset.state=kind;
  if(label) label.textContent=kind==='ok'?'Git đã lưu':kind==='syncing'?'Đang sync…':kind==='error'?'Lỗi Git':'Git Sync';
}
function openGitModal(){
  const c=getBeerichGitConfig();
  document.getElementById('gitTokenInput').value=c.token||'';
  document.getElementById('gitRepoInput').value=c.repo||detectBeerichGitRepo();
  document.getElementById('gitBranchInput').value=c.branch||'';
  document.getElementById('gitPathInput').value=c.path||'beerich-finance-data.json';
  document.getElementById('gitAutoSyncInput').checked=c.autoSync!==false;
  document.getElementById('gitModalBackdrop').classList.add('show');
  beerichGitMessage(beerichGitConfigured()?'Đã có cấu hình. Bạn có thể đẩy hoặc tải dữ liệu.':'Chưa cấu hình GitHub. Hãy nhập Token và Repository.', beerichGitConfigured()?'ok':'idle');
}
function closeGitModal(){document.getElementById('gitModalBackdrop').classList.remove('show');}
function disconnectGitConfig(){
  localStorage.removeItem(BEERICH_GIT_CONFIG_KEY);
  if(beerichGitPushTimer) clearTimeout(beerichGitPushTimer);
  beerichGitMessage('Đã ngắt kết nối GitHub. Dữ liệu trên máy vẫn được giữ nguyên.','idle');
  beerichToast('Đã ngắt kết nối GitHub.');
}
function utf8ToBase64Git(str){const bytes=new TextEncoder().encode(str);let binary='';for(let i=0;i<bytes.length;i++)binary+=String.fromCharCode(bytes[i]);return btoa(binary);}
function base64ToUtf8Git(b64){const binary=atob(String(b64||'').replace(/\s/g,''));const bytes=new Uint8Array(binary.length);for(let i=0;i<binary.length;i++)bytes[i]=binary.charCodeAt(i);return new TextDecoder().decode(bytes);}
function beerichGitApiUrl(c){
  const path=String(c.path||'beerich-finance-data.json').split('/').filter(Boolean).map(encodeURIComponent).join('/');
  const base=`https://api.github.com/repos/${c.repo}/contents/${path}`;
  return c.branch?`${base}?ref=${encodeURIComponent(c.branch)}&t=${Date.now()}`:`${base}?t=${Date.now()}`;
}
function beerichGitHeaders(c){return {'Authorization':`Bearer ${c.token}`,'Accept':'application/vnd.github+json','X-GitHub-Api-Version':'2022-11-28'};}
function scheduleBeerichGitPush(reason='Tự động lưu BeeRich'){
  if(gitPullApplying) return;
  const c=getBeerichGitConfig();
  if(!c.token||!c.repo||!c.repo.includes('/')||c.autoSync===false) return;
  if(beerichGitPushTimer) clearTimeout(beerichGitPushTimer);
  beerichGitMessage('Đã lưu trên máy; đang chờ đồng bộ GitHub…','syncing');
  beerichGitPushTimer=setTimeout(()=>gitPushData(false,reason),1200);
}
async function gitPushData(manual=false, reason='Cập nhật dữ liệu BeeRich'){
  const c=getBeerichGitConfig();
  if(!c.token||!c.repo||!c.repo.includes('/')){if(manual)beerichToast('Hãy cấu hình GitHub Token và Repository trước.');beerichGitMessage('Chưa cấu hình GitHub.');return false;}
  if(beerichGitBusy)return false;
  beerichGitBusy=true;beerichGitMessage('Đang đẩy dữ liệu lên GitHub…','syncing');
  try{
    const url=beerichGitApiUrl(c), headers=beerichGitHeaders(c);
    const get=await fetch(url,{headers,cache:'no-store'});let sha=null;
    if(get.ok){sha=(await get.json()).sha;}else if(get.status!==404){const d=await get.json().catch(()=>({}));throw new Error(d.message||`GitHub HTTP ${get.status}`);}
    const stamp=new Date().toLocaleString('vi-VN');
    const payload={app:'BeeRich Finance',version:1,updatedAt:Date.now(),updatedAtText:stamp,finances};
    const body={message:`${reason} (${stamp})`,content:utf8ToBase64Git(JSON.stringify(payload,null,2))};
    if(sha)body.sha=sha;if(c.branch)body.branch=c.branch;
    const put=await fetch(url.split('?')[0],{method:'PUT',headers:{...headers,'Content-Type':'application/json'},body:JSON.stringify(body)});
    if(!put.ok){const d=await put.json().catch(()=>({}));throw new Error(d.message||`GitHub HTTP ${put.status}`);}
    beerichGitMessage(`Đã đồng bộ lên GitHub lúc ${stamp}.`,'ok');if(manual)beerichToast('Đã đẩy dữ liệu BeeRich lên GitHub.');return true;
  }catch(err){console.error('BeeRich Git push:',err);beerichGitMessage(`Lỗi đồng bộ: ${err.message}`,'error');if(manual)beerichToast(`Không thể đẩy dữ liệu: ${err.message}`);return false;}
  finally{beerichGitBusy=false;}
}
async function gitPullData(manual=false){
  const c=getBeerichGitConfig();
  if(!c.token||!c.repo||!c.repo.includes('/')){if(manual)beerichToast('Hãy cấu hình GitHub Token và Repository trước.');beerichGitMessage('Chưa cấu hình GitHub.');return false;}
  if(beerichGitBusy)return false;
  beerichGitBusy=true;beerichGitMessage('Đang tải dữ liệu từ GitHub…','syncing');
  try{
    const res=await fetch(beerichGitApiUrl(c),{headers:beerichGitHeaders(c),cache:'no-store'});
    if(res.status===404){beerichGitMessage('Chưa có file dữ liệu trên Git; đang tạo từ dữ liệu trên máy.','syncing');beerichGitBusy=false;return await gitPushData(manual,'Khởi tạo dữ liệu BeeRich trên GitHub');}
    if(!res.ok){const d=await res.json().catch(()=>({}));throw new Error(d.message||`GitHub HTTP ${res.status}`);}
    const meta=await res.json();const payload=JSON.parse(base64ToUtf8Git(meta.content));
    const incoming=payload.finances || payload.data || null;
    if(!incoming||typeof incoming!=='object')throw new Error('File Git không có dữ liệu BeeRich hợp lệ.');
    const next={...defaults,...incoming};
    next.currentMoney=Number(next.currentMoney)||0;next.savings=Number(next.savings)||0;next.gold=Number(next.gold)||0;next.hideCurrentMoney=Boolean(next.hideCurrentMoney);
    if(!Array.isArray(next.transactions))next.transactions=[];
    next.transactions=next.transactions.filter(t=>t&&typeof t==='object'&&t.date&&Number.isFinite(Number(t.amount))&&(t.type==='income'||t.type==='expense'));
    gitPullApplying=true;finances=next;
    localStorage.setItem(STORAGE_KEY,JSON.stringify(finances));
    setTab(activeTab);
    gitPullApplying=false;
    beerichGitMessage(`Đã tải dữ liệu từ GitHub (${payload.updatedAtText||'bản mới nhất'}).`,'ok');if(manual)beerichToast('Đã tải dữ liệu mới nhất từ GitHub.');return true;
  }catch(err){gitPullApplying=false;console.error('BeeRich Git pull:',err);beerichGitMessage(`Lỗi tải dữ liệu: ${err.message}`,'error');if(manual)beerichToast(`Không thể tải dữ liệu: ${err.message}`);return false;}
  finally{beerichGitBusy=false;}
}
document.getElementById('gitConfigForm').addEventListener('submit',async e=>{
  e.preventDefault();
  const cfg={token:document.getElementById('gitTokenInput').value.trim(),repo:document.getElementById('gitRepoInput').value.trim().replace(/^https?:\/\/github\.com\//i,'').replace(/\.git$/i,''),branch:document.getElementById('gitBranchInput').value.trim(),path:document.getElementById('gitPathInput').value.trim()||'beerich-finance-data.json',autoSync:document.getElementById('gitAutoSyncInput').checked};
  if(!cfg.token||!cfg.repo.includes('/')){beerichToast('Nhập Token và Repository đúng định dạng owner/repo.');return;}
  localStorage.setItem(BEERICH_GIT_CONFIG_KEY,JSON.stringify(cfg));
  const ok=await gitPushData(true,'Lưu cấu hình BeeRich');if(ok)closeGitModal();
});
function beerichToast(message){
  let el=document.getElementById('beerichToast');
  if(!el){el=document.createElement('div');el.id='beerichToast';Object.assign(el.style,{position:'fixed',left:'50%',bottom:'calc(95px + env(safe-area-inset-bottom))',transform:'translateX(-50%)',maxWidth:'calc(100vw - 30px)',padding:'11px 15px',borderRadius:'14px',background:'#14532d',color:'#fff',fontSize:'13px',fontWeight:'650',boxShadow:'0 8px 25px rgba(0,0,0,.2)',zIndex:'100',textAlign:'center'});document.body.appendChild(el);}
  el.textContent=message;el.style.display='block';clearTimeout(el._hideTimer);el._hideTimer=setTimeout(()=>{el.style.display='none';},2800);
}
function initBeerichGitSync(){
  const c=getBeerichGitConfig();
  beerichGitMessage(beerichGitConfigured()?'Đã cấu hình GitHub. Đang kiểm tra bản dữ liệu mới nhất…':'Chưa cấu hình GitHub. Dữ liệu hiện được lưu trên thiết bị này.',beerichGitConfigured()?'syncing':'idle');
  if(beerichGitConfigured()&&c.autoSync!==false) setTimeout(()=>gitPullData(false),450);
}
document.addEventListener('visibilitychange',()=>{
  const c=getBeerichGitConfig();
  if(!document.hidden && c.autoSync!==false && beerichGitConfigured() && !beerichGitBusy && !beerichGitPushTimer) gitPullData(false);
});


setTab('overview');
initBeerichGitSync();
</script>
</body>
</html>
