[restaurant_management_system_ui (1).html](https://github.com/user-attachments/files/29438656/restaurant_management_system_ui.1.html)
# restaurant-management-systems_
<style>
*{box-sizing:border-box;margin:0;padding:0}
.app{display:flex;flex-direction:column;min-height:680px;background:var(--surface-0);border-radius:12px;overflow:hidden;border:0.5px solid var(--border)}
.topbar{background:#B03A2E;padding:10px 18px;display:flex;align-items:center;justify-content:space-between}
.logo{color:#FFD700;font-size:17px;font-weight:500;display:flex;align-items:center;gap:8px}
.user-info{display:flex;align-items:center;gap:10px;color:rgba(255,255,255,0.9);font-size:12px}
.avatar{width:30px;height:30px;border-radius:50%;background:#FFD700;color:#7b2300;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:500}
.layout{display:flex;flex:1}
.nav{width:52px;background:#1a1a1a;display:flex;flex-direction:column;align-items:center;padding:10px 0;gap:4px}
.nav-item{width:40px;height:40px;border-radius:8px;display:flex;flex-direction:column;align-items:center;justify-content:center;cursor:pointer;color:rgba(255,255,255,0.5);font-size:9px;gap:3px;transition:all .15s}
.nav-item i{font-size:18px}
.nav-item.active{background:#B03A2E;color:#FFD700}
.nav-item:not(.active):hover{background:rgba(255,255,255,0.08);color:#fff}
.content{flex:1;display:flex;flex-direction:column;overflow:hidden}
.page{display:none;flex:1;flex-direction:column}
.page.active{display:flex}
.page-header{padding:14px 18px 10px;border-bottom:0.5px solid var(--border);display:flex;align-items:center;justify-content:space-between}
.page-title{font-size:15px;font-weight:500;color:var(--text-primary)}
.page-body{flex:1;padding:14px 18px;overflow-y:auto}
.stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-bottom:16px}
.stat-card{background:var(--surface-1);border-radius:8px;padding:12px 14px}
.stat-label{font-size:11px;color:var(--text-muted);margin-bottom:4px}
.stat-val{font-size:20px;font-weight:500;color:var(--text-primary)}
.stat-val.red{color:#B03A2E}
.stat-val.green{color:#1e8e3e}
.two-col{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.card{background:var(--surface-2);border:0.5px solid var(--border);border-radius:10px;padding:14px}
.card-title{font-size:13px;font-weight:500;color:var(--text-primary);margin-bottom:10px;display:flex;align-items:center;gap:6px}
.table{width:100%;border-collapse:collapse;font-size:12px;table-layout:fixed}
.table th{text-align:left;padding:6px 8px;color:var(--text-muted);font-weight:400;border-bottom:0.5px solid var(--border)}
.table td{padding:7px 8px;color:var(--text-primary);border-bottom:0.5px solid var(--border)}
.table tr:last-child td{border-bottom:none}
.badge{display:inline-block;padding:2px 8px;border-radius:20px;font-size:11px;font-weight:500}
.badge.green{background:#e6f4ea;color:#1e8e3e}
.badge.amber{background:#fef7e0;color:#b06000}
.badge.red{background:#fce8e6;color:#c5221f}
.badge.blue{background:#e8f0fe;color:#1a73e8}
.action-row{display:flex;gap:8px;margin-bottom:12px}
.btn-red{background:#B03A2E;color:#fff;border:none;border-radius:7px;padding:7px 14px;font-size:12px;cursor:pointer;display:flex;align-items:center;gap:5px}
.btn-red:hover{background:#922b21}
.btn-outline{background:transparent;color:var(--text-primary);border:0.5px solid var(--border-strong);border-radius:7px;padding:7px 14px;font-size:12px;cursor:pointer;display:flex;align-items:center;gap:5px}
.btn-outline:hover{background:var(--surface-1)}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px}
.form-group{display:flex;flex-direction:column;gap:4px}
.form-label{font-size:11px;color:var(--text-secondary)}
.inp{width:100%;font-size:13px;padding:7px 10px;border-radius:6px;border:0.5px solid var(--border-strong);background:var(--surface-1);color:var(--text-primary)}
.bill-box{background:var(--surface-1);border-radius:8px;padding:12px;font-size:12px}
.bill-row{display:flex;justify-content:space-between;padding:4px 0;border-bottom:0.5px solid var(--border)}
.bill-row:last-child{border-bottom:none;font-weight:500;font-size:13px;color:#B03A2E;padding-top:8px}
.chart-bar-wrap{display:flex;flex-direction:column;gap:6px}
.chart-row{display:flex;align-items:center;gap:8px;font-size:12px}
.chart-label{width:36px;color:var(--text-secondary);text-align:right;flex-shrink:0}
.chart-bar{height:18px;border-radius:4px;background:#B03A2E;opacity:0.85;transition:width .4s}
.chart-val{color:var(--text-secondary);font-size:11px;white-space:nowrap}
.login-wrap{display:flex;align-items:center;justify-content:center;flex:1;background:var(--surface-0)}
.login-card{background:var(--surface-2);border:0.5px solid var(--border);border-radius:14px;padding:28px 28px;width:320px;display:flex;flex-direction:column;gap:14px}
.login-logo{text-align:center;font-size:20px;font-weight:500;color:#B03A2E;display:flex;align-items:center;justify-content:center;gap:8px}
.login-logo i{color:#FFD700;background:#B03A2E;padding:7px;border-radius:8px}
.login-sub{text-align:center;font-size:12px;color:var(--text-muted)}
.role-pills{display:flex;gap:6px;flex-wrap:wrap}
.role-pill{padding:4px 12px;border-radius:20px;font-size:12px;border:0.5px solid var(--border-strong);cursor:pointer;color:var(--text-secondary);background:var(--surface-1)}
.role-pill.sel{background:#B03A2E;color:#fff;border-color:#B03A2E}
</style>

<div class="app">
  <div class="topbar">
    <div class="logo"><i class="ti ti-building-store" aria-hidden="true"></i> Magic Restaurant — Management System</div>
    <div class="user-info">
      <div class="avatar">AD</div>
      <div><div style="font-weight:500">Admin</div><div style="opacity:0.7;font-size:11px">Administrator</div></div>
    </div>
  </div>

  <div class="layout">
    <nav class="nav">
      <div class="nav-item active" onclick="showPage('dashboard',this)" title="Dashboard"><i class="ti ti-layout-dashboard" aria-hidden="true"></i><span>Home</span></div>
      <div class="nav-item" onclick="showPage('login',this)" title="Login"><i class="ti ti-lock" aria-hidden="true"></i><span>Login</span></div>
      <div class="nav-item" onclick="showPage('menu',this)" title="Menu"><i class="ti ti-tools-kitchen-2" aria-hidden="true"></i><span>Menu</span></div>
      <div class="nav-item" onclick="showPage('orders',this)" title="Orders"><i class="ti ti-clipboard-list" aria-hidden="true"></i><span>Orders</span></div>
      <div class="nav-item" onclick="showPage('billing',this)" title="Billing"><i class="ti ti-receipt" aria-hidden="true"></i><span>Billing</span></div>
      <div class="nav-item" onclick="showPage('customers',this)" title="Customers"><i class="ti ti-users" aria-hidden="true"></i><span>Customers</span></div>
      <div class="nav-item" onclick="showPage('employees',this)" title="Employees"><i class="ti ti-id-badge" aria-hidden="true"></i><span>Staff</span></div>
      <div class="nav-item" onclick="showPage('reports',this)" title="Reports"><i class="ti ti-chart-bar" aria-hidden="true"></i><span>Reports</span></div>
    </nav>

    <div class="content">

      <!-- DASHBOARD -->
      <div class="page active" id="pg-dashboard">
        <div class="page-header"><span class="page-title">Dashboard overview</span><span style="font-size:12px;color:var(--text-muted)">Today, 26 Jun 2026</span></div>
        <div class="page-body">
          <div class="stats-row">
            <div class="stat-card"><div class="stat-label">Today's revenue</div><div class="stat-val red">৳18,450</div></div>
            <div class="stat-card"><div class="stat-label">Orders today</div><div class="stat-val">42</div></div>
            <div class="stat-card"><div class="stat-label">Customers</div><div class="stat-val">38</div></div>
            <div class="stat-card"><div class="stat-label">Active staff</div><div class="stat-val green">7</div></div>
          </div>
          <div class="two-col">
            <div class="card">
              <div class="card-title"><i class="ti ti-clipboard-list" style="font-size:15px;color:#B03A2E" aria-hidden="true"></i> Recent orders</div>
              <table class="table"><thead><tr><th>Order</th><th>Items</th><th>Total</th><th>Status</th></tr></thead><tbody>
                <tr><td>#1042</td><td>3</td><td>৳520</td><td><span class="badge green">Done</span></td></tr>
                <tr><td>#1041</td><td>5</td><td>৳780</td><td><span class="badge amber">Cooking</span></td></tr>
                <tr><td>#1040</td><td>2</td><td>৳310</td><td><span class="badge green">Done</span></td></tr>
                <tr><td>#1039</td><td>4</td><td>৳640</td><td><span class="badge blue">Pending</span></td></tr>
              </tbody></table>
            </div>
            <div class="card">
              <div class="card-title"><i class="ti ti-star" style="font-size:15px;color:#B03A2E" aria-hidden="true"></i> Top selling items</div>
              <div class="chart-bar-wrap">
                <div class="chart-row"><span class="chart-label">Burger</span><div class="chart-bar" style="width:75%"></div><span class="chart-val">75 sold</span></div>
                <div class="chart-row"><span class="chart-label">Fries</span><div class="chart-bar" style="width:60%"></div><span class="chart-val">60 sold</span></div>
                <div class="chart-row"><span class="chart-label">Cola</span><div class="chart-bar" style="width:50%"></div><span class="chart-val">50 sold</span></div>
                <div class="chart-row"><span class="chart-label">Pizza</span><div class="chart-bar" style="width:35%"></div><span class="chart-val">35 sold</span></div>
                <div class="chart-row"><span class="chart-label">Lassi</span><div class="chart-bar" style="width:25%"></div><span class="chart-val">25 sold</span></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- LOGIN -->
      <div class="page" id="pg-login">
        <div class="login-wrap">
          <div class="login-card">
            <div class="login-logo"><i class="ti ti-building-store" aria-hidden="true"></i> Magic Restaurant</div>
            <div class="login-sub">Sign in to your account</div>
            <div class="form-group"><span class="form-label">Username</span><input class="inp" type="text" placeholder="admin@magic.com" value="admin@magic.com"></div>
            <div class="form-group"><span class="form-label">Password</span><input class="inp" type="password" placeholder="••••••••" value="password"></div>
            <div>
              <div class="form-label" style="margin-bottom:6px">Login as</div>
              <div class="role-pills">
                <div class="role-pill sel" onclick="selRole(this)">Admin</div>
                <div class="role-pill" onclick="selRole(this)">Manager</div>
                <div class="role-pill" onclick="selRole(this)">Cashier</div>
                <div class="role-pill" onclick="selRole(this)">Waiter</div>
              </div>
            </div>
            <button class="btn-red" style="width:100%;justify-content:center;padding:10px;" onclick="showPage('dashboard',null)"><i class="ti ti-login" aria-hidden="true"></i> Sign in</button>
            <div style="font-size:11px;color:var(--text-muted);text-align:center">OOP concept: Inheritance — Admin, Manager, Cashier extend User</div>
          </div>
        </div>
      </div>

      <!-- MENU -->
      <div class="page" id="pg-menu">
        <div class="page-header"><span class="page-title">Menu management</span>
          <button class="btn-red" onclick=""><i class="ti ti-plus" aria-hidden="true"></i> Add item</button>
        </div>
        <div class="page-body">
          <div class="action-row">
            <select class="inp" style="width:auto"><option>All categories</option><option>Burgers</option><option>Pizza</option><option>Drinks</option><option>Fries</option><option>Desserts</option></select>
            <input class="inp" style="flex:1" placeholder="Search menu items...">
          </div>
          <table class="table">
            <thead><tr><th style="width:30%">Item name</th><th style="width:18%">Category</th><th style="width:15%">Price</th><th style="width:15%">Class type</th><th style="width:22%">Actions</th></tr></thead>
            <tbody>
              <tr><td>Classic Beef Burger</td><td>Burgers</td><td>৳180</td><td><span class="badge blue">FoodItem</span></td><td><button class="btn-outline" style="padding:4px 10px"><i class="ti ti-edit" style="font-size:13px" aria-hidden="true"></i> Edit</button></td></tr>
              <tr><td>Margherita Pizza</td><td>Pizza</td><td>৳250</td><td><span class="badge blue">FoodItem</span></td><td><button class="btn-outline" style="padding:4px 10px"><i class="ti ti-edit" style="font-size:13px" aria-hidden="true"></i> Edit</button></td></tr>
              <tr><td>Cola Large</td><td>Drinks</td><td>৳60</td><td><span class="badge amber">DrinkItem</span></td><td><button class="btn-outline" style="padding:4px 10px"><i class="ti ti-edit" style="font-size:13px" aria-hidden="true"></i> Edit</button></td></tr>
              <tr><td>Mango Juice</td><td>Drinks</td><td>৳80</td><td><span class="badge amber">DrinkItem</span></td><td><button class="btn-outline" style="padding:4px 10px"><i class="ti ti-edit" style="font-size:13px" aria-hidden="true"></i> Edit</button></td></tr>
              <tr><td>Cheese Fries</td><td>Fries</td><td>৳100</td><td><span class="badge blue">FoodItem</span></td><td><button class="btn-outline" style="padding:4px 10px"><i class="ti ti-edit" style="font-size:13px" aria-hidden="true"></i> Edit</button></td></tr>
              <tr><td>Burger+Fries+Drink Combo</td><td>Combos</td><td>৳280</td><td><span class="badge green">ComboItem</span></td><td><button class="btn-outline" style="padding:4px 10px"><i class="ti ti-edit" style="font-size:13px" aria-hidden="true"></i> Edit</button></td></tr>
            </tbody>
          </table>
          <div style="font-size:11px;color:var(--text-muted);margin-top:10px">OOP concept: Abstraction + Inheritance — MenuItem (abstract) → FoodItem, DrinkItem, ComboItem</div>
        </div>
      </div>

      <!-- ORDERS -->
      <div class="page" id="pg-orders">
        <div class="page-header"><span class="page-title">Order management</span>
          <button class="btn-red"><i class="ti ti-plus" aria-hidden="true"></i> New order</button>
        </div>
        <div class="page-body">
          <div class="action-row">
            <select class="inp" style="width:auto"><option>All types</option><option>Dine-in</option><option>Takeaway</option></select>
            <select class="inp" style="width:auto"><option>All status</option><option>Pending</option><option>Cooking</option><option>Done</option></select>
          </div>
          <table class="table">
            <thead><tr><th>Order ID</th><th>Customer</th><th>Type</th><th>Items</th><th>Total</th><th>Status</th></tr></thead>
            <tbody>
              <tr><td>#1042</td><td>Rahim Ahmed</td><td><span class="badge blue">Dine-in</span></td><td>3 items</td><td>৳520</td><td><span class="badge green">Done</span></td></tr>
              <tr><td>#1041</td><td>Sumaya Begum</td><td><span class="badge amber">Takeaway</span></td><td>5 items</td><td>৳780</td><td><span class="badge amber">Cooking</span></td></tr>
              <tr><td>#1040</td><td>Walk-in</td><td><span class="badge blue">Dine-in</span></td><td>2 items</td><td>৳310</td><td><span class="badge green">Done</span></td></tr>
              <tr><td>#1039</td><td>Karim Mia</td><td><span class="badge amber">Takeaway</span></td><td>4 items</td><td>৳640</td><td><span class="badge red">Pending</span></td></tr>
            </tbody>
          </table>
          <div style="font-size:11px;color:var(--text-muted);margin-top:10px">OOP concept: Polymorphism — Order (abstract) → DineInOrder, TakeawayOrder each override calculateTotal()</div>
        </div>
      </div>

      <!-- BILLING -->
      <div class="page" id="pg-billing">
        <div class="page-header"><span class="page-title">Billing system</span></div>
        <div class="page-body">
          <div class="two-col">
            <div class="card">
              <div class="card-title"><i class="ti ti-receipt" style="font-size:15px;color:#B03A2E" aria-hidden="true"></i> Generate bill — Order #1042</div>
              <div class="bill-box">
                <div class="bill-row"><span>Classic Beef Burger × 1</span><span>৳180</span></div>
                <div class="bill-row"><span>Cheese Fries × 1</span><span>৳100</span></div>
                <div class="bill-row"><span>Cola Large × 1</span><span>৳60</span></div>
                <div class="bill-row"><span style="color:var(--text-muted)">Subtotal</span><span>৳340</span></div>
                <div class="bill-row"><span style="color:var(--text-muted)">VAT (15%)</span><span>৳51</span></div>
                <div class="bill-row"><span style="color:var(--text-muted)">Discount (5%)</span><span>−৳17</span></div>
                <div class="bill-row"><span>Grand total</span><span>৳374</span></div>
              </div>
              <div style="display:flex;gap:8px;margin-top:10px">
                <button class="btn-red"><i class="ti ti-printer" aria-hidden="true"></i> Print bill</button>
                <button class="btn-outline"><i class="ti ti-download" aria-hidden="true"></i> Save PDF</button>
              </div>
            </div>
            <div class="card">
              <div class="card-title"><i class="ti ti-cash" style="font-size:15px;color:#B03A2E" aria-hidden="true"></i> Payment</div>
              <div class="form-group" style="margin-bottom:10px"><span class="form-label">Payment method</span>
                <select class="inp"><option>Cash</option><option>bKash</option><option>Nagad</option><option>Card</option></select>
              </div>
              <div class="form-group" style="margin-bottom:10px"><span class="form-label">Amount received</span><input class="inp" type="number" placeholder="৳400"></div>
              <div class="bill-box" style="margin-bottom:10px">
                <div class="bill-row"><span>Total due</span><span>৳374</span></div>
                <div class="bill-row"><span>Received</span><span>৳400</span></div>
                <div class="bill-row"><span>Change</span><span style="color:#1e8e3e">৳26</span></div>
              </div>
              <button class="btn-red" style="width:100%;justify-content:center"><i class="ti ti-check" aria-hidden="true"></i> Confirm payment</button>
              <div style="font-size:11px;color:var(--text-muted);margin-top:8px">OOP concept: Encapsulation — Bill class wraps Order with tax/discount logic</div>
            </div>
          </div>
        </div>
      </div>

      <!-- CUSTOMERS -->
      <div class="page" id="pg-customers">
        <div class="page-header"><span class="page-title">Customer management</span>
          <button class="btn-red"><i class="ti ti-user-plus" aria-hidden="true"></i> Add customer</button>
        </div>
        <div class="page-body">
          <input class="inp" style="margin-bottom:12px" placeholder="Search by name or phone...">
          <table class="table">
            <thead><tr><th>Name</th><th>Phone</th><th>Total orders</th><th>Points</th><th>Status</th></tr></thead>
            <tbody>
              <tr><td>Rahim Ahmed</td><td>01711-000001</td><td>12</td><td><span class="badge amber">240 pts</span></td><td><span class="badge green">Regular</span></td></tr>
              <tr><td>Sumaya Begum</td><td>01811-000002</td><td>8</td><td><span class="badge amber">160 pts</span></td><td><span class="badge green">Regular</span></td></tr>
              <tr><td>Karim Mia</td><td>01911-000003</td><td>25</td><td><span class="badge red">500 pts</span></td><td><span class="badge blue">VIP</span></td></tr>
              <tr><td>Nasrin Akter</td><td>01611-000004</td><td>3</td><td><span class="badge amber">60 pts</span></td><td><span class="badge green">New</span></td></tr>
            </tbody>
          </table>
          <div style="font-size:11px;color:var(--text-muted);margin-top:10px">OOP concept: Encapsulation — Customer class stores private fields with loyalty point methods</div>
        </div>
      </div>

      <!-- EMPLOYEES -->
      <div class="page" id="pg-employees">
        <div class="page-header"><span class="page-title">Employee management</span>
          <button class="btn-red"><i class="ti ti-user-plus" aria-hidden="true"></i> Add employee</button>
        </div>
        <div class="page-body">
          <table class="table">
            <thead><tr><th>Name</th><th>Role</th><th>Shift</th><th>Salary</th><th>Status</th></tr></thead>
            <tbody>
              <tr><td>Priti Singha</td><td><span class="badge blue">Admin</span></td><td>Morning</td><td>৳25,000</td><td><span class="badge green">Active</span></td></tr>
              <tr><td>Rafiq Islam</td><td><span class="badge amber">Manager</span></td><td>Morning</td><td>৳18,000</td><td><span class="badge green">Active</span></td></tr>
              <tr><td>Taslima Khatun</td><td><span class="badge green">Cashier</span></td><td>Evening</td><td>৳12,000</td><td><span class="badge green">Active</span></td></tr>
              <tr><td>Jamal Hossain</td><td><span class="badge red">Waiter</span></td><td>Evening</td><td>৳9,000</td><td><span class="badge amber">On leave</span></td></tr>
              <tr><td>Mita Roy</td><td><span class="badge red">Waiter</span></td><td>Morning</td><td>৳9,000</td><td><span class="badge green">Active</span></td></tr>
            </tbody>
          </table>
          <div style="font-size:11px;color:var(--text-muted);margin-top:10px">OOP concept: Inheritance — Employee (abstract) → Admin, Manager, Cashier, Waiter each extend User</div>
        </div>
      </div>

      <!-- REPORTS -->
      <div class="page" id="pg-reports">
        <div class="page-header"><span class="page-title">Sales report</span>
          <div style="display:flex;gap:8px">
            <select class="inp" style="width:auto;font-size:12px"><option>This week</option><option>This month</option><option>Today</option></select>
            <button class="btn-red"><i class="ti ti-download" aria-hidden="true"></i> Export</button>
          </div>
        </div>
        <div class="page-body">
          <div class="stats-row">
            <div class="stat-card"><div class="stat-label">Weekly revenue</div><div class="stat-val red">৳1,12,800</div></div>
            <div class="stat-card"><div class="stat-label">Total orders</div><div class="stat-val">286</div></div>
            <div class="stat-card"><div class="stat-label">Avg order value</div><div class="stat-val">৳394</div></div>
            <div class="stat-card"><div class="stat-label">Top item</div><div class="stat-val" style="font-size:14px">Burger</div></div>
          </div>
          <div class="card">
            <div class="card-title"><i class="ti ti-chart-bar" style="font-size:15px;color:#B03A2E" aria-hidden="true"></i> Daily revenue — this week</div>
            <div class="chart-bar-wrap">
              <div class="chart-row"><span class="chart-label">Sun</span><div class="chart-bar" style="width:55%"></div><span class="chart-val">৳13,200</span></div>
              <div class="chart-row"><span class="chart-label">Mon</span><div class="chart-bar" style="width:70%"></div><span class="chart-val">৳16,800</span></div>
              <div class="chart-row"><span class="chart-label">Tue</span><div class="chart-bar" style="width:62%"></div><span class="chart-val">৳14,900</span></div>
              <div class="chart-row"><span class="chart-label">Wed</span><div class="chart-bar" style="width:80%"></div><span class="chart-val">৳19,200</span></div>
              <div class="chart-row"><span class="chart-label">Thu</span><div class="chart-bar" style="width:75%"></div><span class="chart-val">৳18,000</span></div>
              <div class="chart-row"><span class="chart-label">Fri</span><div class="chart-bar" style="width:90%"></div><span class="chart-val">৳21,600</span></div>
              <div class="chart-row"><span class="chart-label">Sat</span><div class="chart-bar" style="width:85%"></div><span class="chart-val">৳9,100</span></div>
            </div>
          </div>
          <div style="font-size:11px;color:var(--text-muted);margin-top:10px">OOP concept: Encapsulation — SalesReport reads ArrayList&lt;Order&gt; and generates stats via methods</div>
        </div>
      </div>

    </div>
  </div>
</div>

<script>
function showPage(id, navEl) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById('pg-'+id).classList.add('active');
  if (navEl) {
    document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
    navEl.classList.add('active');
  }
}
function selRole(el) {
  document.querySelectorAll('.role-pill').forEach(p => p.classList.remove('sel'));
  el.classList.add('sel');
}
</script>
