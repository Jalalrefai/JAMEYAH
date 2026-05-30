[5/30/2026 9:58 PM] jalal files: <!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة سهم | الإدارة الاحترافية للجمعيات المالية</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600&family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Tajawal', sans-serif; }
        .num-font { font-family: 'Plus Jakarta Sans', 'Tajawal', sans-serif; }
        @media print {
            body { background: white; color: black; }
            .no-print { display: none !important; }
            .print-card { border: 1px solid #ccc !important; box-shadow: none !important; }
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col antialiased">

    <header class="bg-slate-900 text-white shadow-lg sticky top-0 z-50 no-print">
        <div class="container mx-auto px-6 py-4 flex flex-col sm:flex-row justify-between items-center gap-4">
            <div class="flex items-center gap-3">
                <div class="bg-emerald-500 p-2.5 rounded-xl shadow-md shadow-emerald-500/20">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-slate-950" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                    </svg>
                </div>
                <div>
                    <h1 class="text-xl font-extrabold tracking-tight flex items-center gap-2">منصة سَهْم <span class="bg-emerald-500 text-slate-950 text-[10px] font-bold px-2 py-0.5 rounded">PRO</span></h1>
                    <p class="text-xs text-slate-400 mt-0.5">نظام الحسابات والقرعة التكافلية الذكي</p>
                </div>
            </div>
            
            <div class="flex items-center bg-slate-800 rounded-xl p-2 border border-slate-700/60 transition-all">
                <span class="ml-3 text-xs font-semibold text-slate-300">🛡️ وضع المسؤول (الأدمن):</span>
                <label class="relative inline-flex items-center cursor-pointer">
                    <input type="checkbox" id="adminToggle" class="sr-only peer" checked onchange="toggleAdminMode()">
                    <div class="w-11 h-6 bg-slate-600 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:-translate-x-full after:content-[''] after:absolute after:top-[2px] after:right-[2px] after:bg-white after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-emerald-500"></div>
                </label>
            </div>
        </div>
    </header>

    <main class="container mx-auto px-4 sm:px-6 py-8 flex-grow max-w-7xl">
        
        <section class="mb-8 grid grid-cols-1 lg:grid-cols-3 gap-6">
            <div class="bg-gradient-to-br from-slate-900 to-slate-800 text-white p-6 rounded-2xl shadow-md flex flex-col justify-between print-card">
                <div>
                    <span class="text-emerald-400 text-xs font-bold uppercase tracking-wider">متابعة الدورة الزمنية</span>
                    <h3 class="text-lg font-bold mt-1">الشهر المستهدف حالياً:</h3>
                </div>
                <div class="flex items-center justify-between my-4 bg-slate-800/80 rounded-xl p-3 border border-slate-700">
                    <button onclick="changeCurrentMonth(-1)" class="p-2 bg-slate-700 hover:bg-slate-600 text-white rounded-lg transition-all no-print font-bold">◀</button>
                    <span class="text-2xl font-bold num-font text-emerald-400" id="currentMonthLabel">الشهر 1</span>
[5/30/2026 9:58 PM] jalal files: <button onclick="changeCurrentMonth(1)" class="p-2 bg-slate-700 hover:bg-slate-600 text-white rounded-lg transition-all no-print font-bold">▶</button>
                </div>
                <p class="text-xs text-slate-400">تستطيع الانتقال بين الأشهر لتأكيد دفع اشتراكات الأعضاء لشهر معين دون التأثير على البقية.</p>
            </div>

            <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100 lg:col-span-2 grid grid-cols-1 sm:grid-cols-3 gap-4 print-card">
                <div class="bg-slate-50 p-4 rounded-xl flex flex-col justify-center border border-slate-100">
                    <span class="text-slate-500 text-xs font-medium">مستلم القبضة هذا الشهر</span>
                    <span class="text-md font-bold text-slate-900 mt-2 truncate" id="liveBeneficiary">⏳ لم يحدد بعد</span>
                </div>
                <div class="bg-emerald-50/60 p-4 rounded-xl flex flex-col justify-center border border-emerald-100/50">
                    <span class="text-emerald-700 text-xs font-medium">المراد تحصيله هذا الشهر</span>
                    <span class="text-xl font-bold text-emerald-600 mt-1 num-font" id="liveCollected">0 / 0 د.أ</span>
                </div>
                <div class="bg-amber-50/60 p-4 rounded-xl flex flex-col justify-center border border-amber-100/50">
                    <span class="text-amber-700 text-xs font-medium">المبلغ الإجمالي للقبضة</span>
                    <span class="text-xl font-bold text-amber-600 mt-1 num-font" id="statTotalPayout">0 د.أ</span>
                </div>
            </div>
        </section>

        <section class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-8 no-print">
            <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-100">
                <span class="text-slate-400 text-xs font-medium block">قيمة السهم الشهري</span>
                <span class="text-lg font-bold text-slate-800 mt-1 num-font" id="statAmount">0 د.أ</span>
            </div>
            <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-100">
                <span class="text-slate-400 text-xs font-medium block">إجمالي الأعضاء</span>
                <span class="text-lg font-bold text-slate-800 mt-1 num-font" id="statCount">0 أعضاء</span>
            </div>
            <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-100">
                <span class="text-slate-400 text-xs font-medium block">مدة الجمعية الكلية</span>
                <span class="text-lg font-bold text-indigo-600 mt-1 num-font" id="statDuration">0 أشهر</span>
            </div>
            <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-100">
                <span class="text-slate-400 text-xs font-medium block">تاريخ الانطلاق المحدد</span>
                <span class="text-sm font-bold text-slate-800 mt-1.5 block" id="statStartDate">يونيو 2026</span>
            </div>
        </section>

        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            
            <div class="space-y-6 lg:col-span-1 no-print">
                
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                    <h2 class="text-sm font-bold text-slate-900 mb-4 flex items-center gap-2">🛠️ تكوين وإعداد الجمعية</h2>
                    <div class="space-y-4">
                        <div>
                            <label class="block text-xs font-medium text-slate-500 mb-1">المبلغ المالي الشهري للعضو</label>
                            <div class="relative">
                                <input type="number" id="inputAmount" value="500" class="w-full p-2.5 bg-slate-50 border border-slate-200 rounded-xl font-semibold num-font focus:ring-2 focus:ring-emerald-500 focus:bg-white focus:outline-none transition-all" oninput="updateSettings()">
                                <span class="absolute left-3 top-3 text-xs text-slate-400 font-bold">د.أ</span>
                            </div>
                        </div>
                        <div>
[5/30/2026 9:58 PM] jalal files: <label class="block text-xs font-medium text-slate-500 mb-1">تاريخ بداية أول قسط</label>
                            <input type="month" id="inputStartDate" value="2026-06" class="w-full p-2.5 bg-slate-50 border border-slate-200 rounded-xl font-medium text-sm focus:ring-2 focus:ring-emerald-500 focus:bg-white focus:outline-none transition-all" onchange="updateSettings()">
                        </div>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                    <h2 class="text-sm font-bold text-slate-900 mb-4 flex items-center gap-2">👤 تسجيل مشترك جديد</h2>
                    <form id="addMemberForm" onsubmit="addMember(event)" class="space-y-4">
                        <div>
                            <label class="block text-xs font-medium text-slate-500 mb-1">الاسم الثلاثي الكامل</label>
                            <input type="text" id="memberName" required placeholder="مثال: فيصل خالد الحربي" class="w-full p-2.5 border border-slate-200 rounded-xl text-sm focus:ring-2 focus:ring-emerald-500 focus:outline-none transition-all">
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-500 mb-1">رقم الجوال أو الهوية</label>
                            <input type="tel" id="memberPhone" required placeholder="05xxxxxxxx" class="w-full p-2.5 border border-slate-200 rounded-xl text-sm font-medium num-font focus:ring-2 focus:ring-emerald-500 focus:outline-none transition-all">
                        </div>
                        <button type="submit" class="w-full bg-slate-900 hover:bg-slate-800 text-white font-medium py-2.5 rounded-xl text-sm transition-all shadow-sm">
                            إدراج العضو بالنظام
                        </button>
                    </form>
                </div>

                <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                    <h2 class="text-sm font-bold text-slate-900 mb-2 flex items-center gap-2">🎲 سحب القرعة العشوائية</h2>
                    <p class="text-[11px] text-slate-400 leading-relaxed mb-4">تقوم هذه الميزة بتوزيع الأشهر المتبقية تلقائياً وبعشوائية تامة على كافة الأعضاء دفعة واحدة بشفافية كاملة.</p>
                    <button onclick="runLottery()" class="w-full bg-gradient-to-r from-indigo-600 to-purple-600 hover:from-indigo-700 hover:to-purple-700 text-white font-medium py-2.5 rounded-xl text-sm transition-all shadow-md shadow-indigo-600/10">
                        🔀 بدء السحب والقرعة الإلكترونية
                    </button>
                </div>

            </div>

            <div class="lg:col-span-2 space-y-6">
                <div class="bg-white rounded-2xl shadow-sm border border-slate-100 overflow-hidden print-card">
                    
                    <div class="p-6 border-b border-slate-100 bg-slate-50/50 space-y-4 no-print">
                        <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4">
                            <div>
                                <h2 class="text-base font-bold text-slate-900">📊 كشف الترتيب وجدولة الاشتراكات</h2>
                                <p class="text-xs text-slate-400 mt-0.5" id="adminBadge">🛡️ لوحة تحكم المسؤول بكامل الصلاحيات مفعّلة.</p>
                            </div>
                            <button onclick="window.print()" class="bg-white border border-slate-200 text-slate-700 text-xs font-semibold px-4 py-2 rounded-xl hover:bg-slate-50 shadow-sm flex items-center gap-2 transition-all">
                                🖨️ تصدير / طباعة الكشف
                            </button>
                        </div>
                        
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 pt-2">
                            <input type="text" id="tableSearch" oninput="renderMembers()" placeholder="🔍 ابحث بالاسم أو الرقم...
[5/30/2026 9:58 PM] jalal files: " class="p-2 border border-slate-200 rounded-xl text-xs focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                            <select id="tableFilter" onchange="renderMembers()" class="p-2 border border-slate-200 rounded-xl text-xs bg-white focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                                <option value="all">كل الأعضاء بلا استثناء</option>
                                <option value="paidThisMonth">من دفعوا (الشهر الحالي)</option>
                                <option value="notPaidThisMonth">من لم يدفعوا (الشهر الحالي)</option>
                                <option value="hasTurn">من تحدد شهر استلامهم</option>
                            </select>
                        </div>
                    </div>

                    <div class="overflow-x-auto">
                        <table class="w-full text-right border-collapse">
                            <thead>
                                <tr class="bg-slate-100/70 text-slate-600 text-xs font-bold border-b border-slate-200">
                                    <th class="p-4">المشترك</th>
                                    <th class="p-4">بيانات الاتصال</th>
                                    <th class="p-4">شهر وتاريخ الاستلام</th>
                                    <th class="p-4" id="tableMonthHeader">حالة سداد (شـهر 1)</th>
                                    <th class="p-4 text-center no-print">إجراءات الإدارة</th>
                                </tr>
                            </thead>
                            <tbody id="membersTableBody" class="divide-y divide-slate-100 text-xs font-medium">
                                </tbody>
                        </table>
                    </div>
                    
                    <div id="emptyState" class="p-16 text-center text-slate-400 hidden text-sm">
                        📭 لا يوجد مشتركين يطابقون خيارات البحث الحالية. قم بإضافة أعضاء للبدء.
                    </div>
                </div>

                <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 no-print">
                    <h3 class="text-xs font-bold text-slate-900 mb-3 flex items-center gap-2">📝 سجل حركات النظام الحالي:</h3>
                    <div id="activityLogs" class="space-y-1.5 max-h-32 overflow-y-auto text-[11px] font-mono text-slate-500 pr-1">
                        </div>
                </div>

            </div>

        </div>
    </main>

    <footer class="text-center py-6 text-xs text-slate-400 border-t border-slate-100 bg-white mt-auto no-print">
        منصة سهم الاحترافية لإدارة الجمعيات والأموال التكافلية © 2026
    </footer>

    <script>
        // قاعدة البيانات والمحاكاة الذكية للنظام
        let state = {
            monthlyAmount: 500,
            startDate: "2026-06",
            currentMonth: 1,
            isAdmin: true,
            members: [
                { id: 1, name: "عبدالله بن فهد العتيبي", phone: "0501234567", turn: 1, paidMonths: [1] },
                { id: 2, name: "أ. سارة عبد العزيز الأحمد", phone: "0507654321", turn: 2, paidMonths: [1] },
                { id: 3, name: "المهندس محمد الشمري", phone: "0559876543", turn: 3, paidMonths: [] },
                { id: 4, name: "د. خالد وليد الجابري", phone: "0561122334", turn: 4, paidMonths: [] }
            ]
        };

        const arabicMonths = ["يناير", "فبراير", "مارس", "أبريل", "مايو", "يونيو", "يوليو", "أغسطس", "سبتمبر", "أكتوبر", "نوفمبر", "ديسمبر"];

        function logActivity(text) {
            const container = document.getElementById('activityLogs');
            const time = new Date().toLocaleTimeString('ar-EG', { hour12: false });
            const logItem = document.createElement('div');
            logItem.className = "py-0.5 border-b border-slate-50 flex justify-between";
            logItem.innerHTML = <span>⚡ ${text}</span> <span class="text-slate-300">${time}</span>;
            container.insertBefore(logItem, container.firstChild);
        }

        function calculateMonthDate(turnNumber) {
[5/30/2026 9:58 PM] jalal files: if (!turnNumber) return "⏳ لم يحدد بعد";
            const [year, month] = state.startDate.split('-').map(Number);
            const calculatedDate = new Date(year, (month - 1) + (turnNumber - 1), 1);
            return ${arabicMonths[calculatedDate.getMonth()]} ${calculatedDate.getFullYear()};
        }

        function updateStats() {
            const count = state.members.length;
            const amount = state.monthlyAmount;
            
            document.getElementById('statAmount').innerText = ${amount.toLocaleString()} د.أ;
            document.getElementById('statCount').innerText = ${count} مشتركين;
            document.getElementById('statDuration').innerText = ${count} أشهر;
            document.getElementById('statTotalPayout').innerText = ${(amount * count).toLocaleString()} د.أ;
            
            if(state.startDate) {
                const [y, m] = state.startDate.split('-').map(Number);
                document.getElementById('statStartDate').innerText = ${arabicMonths[m-1]} ${y};
            }

            document.getElementById('currentMonthLabel').innerText = الشهر ${state.currentMonth};
            document.getElementById('tableMonthHeader').innerText = حالة سداد (شهر ${state.currentMonth});
            
            const beneficiary = state.members.find(m => m.turn === state.currentMonth);
            document.getElementById('liveBeneficiary').innerText = beneficiary ? beneficiary.name : "⏳ لم يحدد بالقرعة";

            const paidCountThisMonth = state.members.filter(m => m.paidMonths.includes(state.currentMonth)).length;
            document.getElementById('liveCollected').innerText = ${(paidCountThisMonth * amount).toLocaleString()} / ${(count * amount).toLocaleString()} د.أ;

            if (count === 0) {
                document.getElementById('emptyState').classList.remove('hidden');
            } else {
                document.getElementById('emptyState').classList.add('hidden');
            }
        }

        function updateSettings() {
            const amt = parseFloat(document.getElementById('inputAmount').value);
            state.monthlyAmount = isNaN(amt) ? 0 : amt;
            state.startDate = document.getElementById('inputStartDate').value || "2026-06";
            
            updateStats();
            renderMembers();
        }

        function changeCurrentMonth(step) {
            const newMonth = state.currentMonth + step;
            if (newMonth >= 1 && newMonth <= Math.max(state.members.length, 1)) {
                state.currentMonth = newMonth;
                updateStats();
                renderMembers();
                logActivity(`تم الانتقال في عرض الحسابات إلى: الشهر ${state.currentMonth}`);
            }
        }

        function addMember(event) {
            event.preventDefault();
            const nameInput = document.getElementById('memberName');
            const phoneInput = document.getElementById('memberPhone');
            
            const newMember = {
                id: Date.now(),
                name: nameInput.value,
                phone: phoneInput.value,
                turn: null,
                paidMonths: []
            };
            
            state.members.push(newMember);
            logActivity(`تمت إضافة العضو الجديد: [ ${newMember.name} ]`);
            
            nameInput.value = '';
            phoneInput.value = '';
            
            updateStats();
            renderMembers();
        }

        function runLottery() {
            if (state.members.length === 0) {
                alert("الرجاء إدخال أسماء المشتركين أولاً لإجراء سحب القرعة.");
                return;
            }
            
            let availableTurns = Array.from({length: state.members.length}, (_, i) => i + 1);
            
            for (let i = availableTurns.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [availableTurns[i], availableTurns[j]] = [availableTurns[j], availableTurns[i]];
            }
            
            state.members.
[5/30/2026 9:58 PM] jalal files: forEach((member, index) => {
                member.turn = availableTurns[index];
            });
            
            logActivity(`🎲 تم إجراء القرعة الآلية العشوائية بنجاح لجميع المشتركين.`);
            updateStats();
            renderMembers();
        }

        function changeTurnHandly(memberId, newTurnValue) {
            const targetMember = state.members.find(m => m.id === memberId);
            const val = parseInt(newTurnValue) || null;
            if (targetMember) {
                targetMember.turn = val;
                logActivity(`تعديل إداري: تم تغيير دور العضو [ ${targetMember.name} ] إلى الشهر ${val || 'غير محدد'}`);
                updateStats();
            }
        }

        function togglePaymentForCurrentMonth(memberId) {
            const targetMember = state.members.find(m => m.id === memberId);
            if (targetMember) {
                const index = targetMember.paidMonths.indexOf(state.currentMonth);
                if (index > -1) {
                    targetMember.paidMonths.splice(index, 1);
                    logActivity(`تراجع عن دفع: إلغاء قسط الشهر ${state.currentMonth} للعضو [ ${targetMember.name} ]`);
                } else {
                    targetMember.paidMonths.push(state.currentMonth);
                    logActivity(`تأكيد مالي: قيد قسط الشهر ${state.currentMonth} من العضو [ ${targetMember.name} ]`);
                }
                updateStats();
                renderMembers();
            }
        }

        function toggleAdminMode() {
            state.isAdmin = document.getElementById('adminToggle').checked;
            const badge = document.getElementById('adminBadge');
            
            if (state.isAdmin) {
                badge.innerText = "🛡️ لوحة تحكم المسؤول بكامل الصلاحيات مفعّلة.";
                badge.className = "text-xs text-amber-600 font-semibold mt-0.5";
                logActivity("تم الدخول والتأشير بصلاحيات المسؤول (Admin).");
            } else {
                badge.innerText = "👤 وضع المشترك العادي (عرض البيانات وكشف الحسابات فقط).";
                badge.className = "text-xs text-indigo-500 font-semibold mt-0.5";
                logActivity("تم الخروج إلى وضع المشاهدة المحدود (User Mode).");
            }
            renderMembers();
        }

        function removeMember(memberId) {
            const targetMember = state.members.find(m => m.id === memberId);
            if (targetMember && confirm(`هل أنت متأكد من حذف ${targetMember.name} نهائياً من الجمعية؟`)) {
                state.members = state.members.filter(m => m.id !== memberId);
                logActivity(`حذف عضو: تم استبعاد [ ${targetMember.name} ] من الجمعية.`);
                if(state.currentMonth > state.members.length && state.currentMonth > 1) {
                    state.currentMonth = state.members.length;
                }
                updateStats();
                renderMembers();
            }
        }

        function renderMembers() {
            const tbody = document.getElementById('membersTableBody');
            tbody.innerHTML = '';
            
            const searchQuery = document.getElementById('tableSearch').value.toLowerCase();
            const filterValue = document.getElementById('tableFilter').value;

            let displayedMembers = [...state.members].sort((a, b) => {
                if (a.turn === null) return 1;
                if (b.turn === null) return -1;
                return a.turn - b.turn;
            });

            displayedMembers = displayedMembers.filter(member => {
                const matchesSearch = member.name.toLowerCase().includes(searchQuery) || member.phone.includes(searchQuery);
                
                let matchesFilter = true;
                if (filterValue === "paidThisMonth") {
                    matchesFilter = member.paidMonths.includes(state.currentMonth);
                } else if (filterValue === "notPaidThisMonth") {
                    matchesFilter = !member.paidMonths.includes(state.currentMonth);
                } else if (filterValue === "hasTurn") {
[5/30/2026 9:58 PM] jalal files: matchesFilter = member.turn !== null;
                }

                return matchesSearch && matchesFilter;
            });

            if(displayedMembers.length === 0) {
                document.getElementById('emptyState').classList.remove('hidden');
            } else {
                document.getElementById('emptyState').classList.add('hidden');
            }

            displayedMembers.forEach(member => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50/80 transition-colors border-b border-slate-100";
                
                if (member.turn === state.currentMonth) {
                    tr.className = "bg-emerald-50/40 hover:bg-emerald-50 font-semibold border-b border-emerald-100";
                }

                const isReceiverThisMonth = member.turn === state.currentMonth;
                const nameTd = `<td class="p-4 text-slate-900 font-semibold">
                    <div class="flex items-center gap-2">
                        ${isReceiverThisMonth ? '<span class="text-emerald-600 text-sm">💰</span>' : ''}
                        <div>
                            <div>${member.name}</div>
                            ${isReceiverThisMonth ? '<span class="text-[10px] bg-emerald-600 text-white px-1.5 py-0.2 rounded font-normal">مستلم القبضة</span>' : ''}
                        </div>
                    </div>
                </td>`;
                
                const phoneTd = <td class="p-4 text-slate-500 num-font">${member.phone}</td>;
                
                let turnTd = '';
                if (state.isAdmin) {
                    let options = <option value="">لم يحدد دور</option>;
                    for(let i=1; i<=state.members.length; i++) {
                        options += <option value="${i}" ${member.turn === i ? 'selected' : ''}>الشهر ${i} (${calculateMonthDate(i)})</option>;
                    }
                    turnTd = `<td class="p-4 no-print">
                        <select onchange="changeTurnHandly(${member.id}, this.value)" class="p-2 bg-white border border-slate-200 rounded-xl text-xs font-medium focus:ring-2 focus:ring-emerald-500 focus:outline-none shadow-sm cursor-pointer">
                            ${options}
                        </select>
                    </td>`;
                } else {
                    turnTd = `<td class="p-4 text-slate-700 font-bold">
                        ${member.turn ? <span class="text-indigo-600">الشهر ${member.turn}</span> <span class="text-slate-400 font-normal text-[11px] block mt-0.5">(${calculateMonthDate(member.turn)})</span> : '⏳ في انتظار السحب'}
                    </td>`;
                }
                
                if(state.isAdmin) {
                    turnTd += `<td class="p-4 text-slate-700 font-bold hidden print:table-cell">
                        ${member.turn ? الشهر ${member.turn} (${calculateMonthDate(member.turn)}) : '⏳ لم يحدد'}
                    </td>`;
                }

                const hasPaidThisMonth = member.paidMonths.includes(state.currentMonth);
                const statusBadge = hasPaidThisMonth 
                    ? <span class="inline-flex items-center gap-1 bg-emerald-100 text-emerald-800 text-[11px] px-2.5 py-1 rounded-lg font-bold">✔️ مسدد</span>
                    : <span class="inline-flex items-center gap-1 bg-rose-100 text-rose-800 text-[11px] px-2.5 py-1 rounded-lg font-bold">❌ غير مسدد</span>;
                const statusTd = <td class="p-4">${statusBadge}</td>;
                
                let actionsTd = '';
                if (state.isAdmin) {
                    actionsTd = `<td class="p-4 text-center space-x-1 space-x-reverse no-print">
                        <button onclick="togglePaymentForCurrentMonth(${member.id})" class="text-[11px] font-bold ${hasPaidThisMonth ? 'bg-amber-500 text-white hover:bg-amber-600' : 'bg-emerald-600 text-white hover:bg-emerald-700'} px-3 py-1.5 rounded-xl transition-all shadow-sm">
[5/30/2026 9:58 PM] jalal files: ${hasPaidThisMonth ? 'تراجع عن السداد' : 'قبض القسط 💵'}
                        </button>
                        <button onclick="removeMember(${member.id})" class="text-[11px] font-semibold bg-slate-100 text-slate-600 hover:bg-rose-100 hover:text-rose-700 px-2.5 py-1.5 rounded-xl transition-all">
                            حذف
                        </button>
                    </td>`;
                } else {
                    actionsTd = <td class="p-4 text-center text-slate-400 text-[11px] italic no-print">معاينة فقط</td>;
                }
                
                tr.innerHTML = nameTd + phoneTd + turnTd + statusTd + actionsTd;
                tbody.appendChild(tr);
            });
        }

        updateStats();
        renderMembers();
    </script>
</body>
</html>
