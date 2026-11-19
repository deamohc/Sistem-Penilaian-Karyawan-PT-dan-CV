<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sistem Penilaian Kinerja & Kenaikan Gaji - PT MKK & CV MGM (v11 - Tiered Late & Alpha Rules)</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Alpine.js -->
  <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.13.3/dist/cdn.min.js"></script>
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>
  <!-- SheetJS -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
    body { font-family: 'Inter', sans-serif; }
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: #f1f5f9; }
    ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 9999px; }
    ::-webkit-scrollbar-thumb:hover { background: #94a3b8; }
    @media print {
      .no-print { display: none !important; }
      body { background: white !important; color: black !important; }
      .print-shadow-none { box-shadow: none !important; border: 1px solid #cbd5e1 !important; }
    }
  </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col" x-data="appraisalApp()" x-init="initApp()">
 
  <!-- Toast Notification -->
  <div x-show="toast.show" x-transition.opacity.duration.300ms
       class="fixed bottom-5 right-5 z-50 flex items-center gap-3 px-4 py-3 rounded-xl shadow-lg border text-sm font-medium no-print"
       :class="toast.type === 'success' ? 'bg-emerald-600 text-white border-emerald-700' : (toast.type === 'warning' ? 'bg-amber-500 text-white border-amber-600' : 'bg-slate-800 text-white border-slate-700')"
       style="display: none;">
    <i :data-lucide="toast.type === 'success' ? 'check-circle-2' : 'info'" class="w-5 h-5 shrink-0"></i>
    <span x-text="toast.message"></span>
  </div>
 
  <!-- =================================================================== -->
  <!-- HALAMAN LOGIN (MUNCUL SAAT BELUM LOGIN)                             -->
  <!-- =================================================================== -->
  <div x-show="!currentUser" class="min-h-screen flex items-center justify-center bg-gradient-to-br from-slate-900 via-slate-800 to-emerald-950 p-4">
    <div class="bg-white w-full max-w-md rounded-3xl shadow-2xl border border-slate-200 overflow-hidden">
      <div class="p-8 bg-gradient-to-r from-emerald-600 to-teal-700 text-white text-center space-y-2">
        <div class="w-14 h-14 rounded-2xl bg-white/20 backdrop-blur flex items-center justify-center mx-auto shadow-inner">
          <i data-lucide="shield-check" class="w-8 h-8 text-white"></i>
        </div>
        <h1 class="text-xl font-extrabold tracking-tight">Portal Penilaian Kinerja</h1>
        <p class="text-xs text-emerald-100">PT Medika Kesehatan Kerja & CV Medika Group Mandiri</p>
      </div>
 
      <form @submit.prevent="handleLogin()" class="p-8 space-y-5">
        <div>
          <label class="block text-xs font-bold text-slate-600 uppercase mb-1.5">Username / ID Login</label>
          <div class="relative">
            <input type="text" required x-model="loginForm.username" placeholder="Masukkan username..." class="w-full pl-10 pr-4 py-3 text-sm bg-slate-50 border border-slate-300 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:outline-none">
            <i data-lucide="user" class="w-4 h-4 text-slate-400 absolute left-3.5 top-3.5"></i>
          </div>
        </div>
 
        <div>
          <label class="block text-xs font-bold text-slate-600 uppercase mb-1.5">Password / PIN</label>
          <div class="relative">
            <input type="password" required x-model="loginForm.password" placeholder="Masukkan password / PIN..." class="w-full pl-10 pr-4 py-3 text-sm bg-slate-50 border border-slate-300 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:outline-none">
            <i data-lucide="lock" class="w-4 h-4 text-slate-400 absolute left-3.5 top-3.5"></i>
          </div>
        </div>
 
        <div x-show="loginError" class="p-3 rounded-xl bg-rose-50 border border-rose-200 text-xs font-semibold text-rose-700 flex items-center gap-2">
          <i data-lucide="alert-circle" class="w-4 h-4 shrink-0"></i>
          <span x-text="loginError"></span>
        </div>
 
        <button type="submit" class="w-full py-3 bg-emerald-600 hover:bg-emerald-700 text-white font-bold text-sm rounded-xl shadow-md transition flex items-center justify-center gap-2">
          <i data-lucide="log-in" class="w-4 h-4"></i><span>Masuk ke Sistem</span>
        </button>
 
        <div class="pt-3 border-t border-slate-100 text-center">
          <p class="text-[11px] text-slate-400">Silakan masukkan Username dan Password yang telah diberikan oleh HRD / Admin.</p>
        </div>
      </form>
    </div>
  </div>
 
  <!-- =================================================================== -->
  <!-- APLIKASI UTAMA (MUNCUL SETELAH LOGIN)                               -->
  <!-- =================================================================== -->
  <div x-show="currentUser" class="flex-grow flex flex-col" style="display: none;">
 
    <!-- Header Navbar -->
    <header class="sticky top-0 z-40 bg-white/95 backdrop-blur border-b border-slate-200 shadow-sm no-print">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-wrap items-center justify-between py-3 gap-3">
          <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-emerald-600 to-teal-700 text-white flex items-center justify-center shadow-md">
              <i data-lucide="award" class="w-6 h-6"></i>
            </div>
            <div>
              <div class="flex items-center gap-2">
                <h1 class="text-base sm:text-lg font-bold text-slate-900 tracking-tight">Performance & Salary Appraisal</h1>
                <span class="px-2 py-0.5 text-xs font-bold rounded-full bg-emerald-100 text-emerald-800 border border-emerald-200" x-text="'Periode ' + settings.year"></span>
              </div>
              <p class="text-xs text-slate-500">PT Medika Kesehatan Kerja (PT MKK) & CV Medika Group Mandiri (CV MGM)</p>
            </div>
          </div>
 
          <!-- User Badge, Backup & Logout -->
          <div class="flex flex-wrap items-center gap-2">
            <!-- Backup & Restore hanya untuk Admin -->
            <template x-if="currentUser && currentUser.role === 'ADMIN'">
              <div class="flex items-center gap-1.5">
                <button @click="exportDataJSON()" title="Unduh file backup JSON agar data aman" class="px-3 py-1.5 bg-amber-50 hover:bg-amber-100 text-amber-800 border border-amber-200 rounded-xl text-xs font-bold transition flex items-center gap-1.5">
                  <i data-lucide="save" class="w-3.5 h-3.5"></i><span>Backup (.json)</span>
                </button>
                <label title="Pulihkan data dari file backup JSON" class="px-3 py-1.5 bg-indigo-50 hover:bg-indigo-100 text-indigo-800 border border-indigo-200 rounded-xl text-xs font-bold transition flex items-center gap-1.5 cursor-pointer">
                  <i data-lucide="folder-up" class="w-3.5 h-3.5"></i><span>Restore (.json)</span>
                  <input type="file" accept=".json" @change="importDataJSON($event)" class="hidden">
                </label>
              </div>
            </template>
 
            <!-- Info User Aktif -->
            <div class="flex items-center gap-2 px-3 py-1.5 rounded-xl border text-xs font-bold" :class="currentUser && currentUser.role === 'ADMIN' ? 'bg-emerald-50 border-emerald-200 text-emerald-900' : 'bg-blue-50 border-blue-200 text-blue-900'">
              <i :data-lucide="currentUser && currentUser.role === 'ADMIN' ? 'shield' : 'user-check'" class="w-3.5 h-3.5"></i>
              <span x-text="currentUser ? currentUser.name : ''"></span>
              <span class="px-1.5 py-0.2 text-[10px] rounded bg-white/80 uppercase" x-text="currentUser && currentUser.role === 'ADMIN' ? 'Admin' : 'Kepala Bagian'"></span>
            </div>
 
            <button @click="handleLogout()" class="px-3 py-1.5 bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 rounded-xl text-xs font-bold transition flex items-center gap-1">
              <i data-lucide="log-out" class="w-3.5 h-3.5"></i><span>Keluar</span>
            </button>
          </div>
 
          <!-- Navigation Tabs (Khusus Admin vs Khusus Kepala Bagian) -->
          <nav class="flex items-center gap-1 bg-slate-100 p-1 rounded-xl overflow-x-auto max-w-full w-full">
            <!-- MENU ADMIN -->
            <template x-if="currentUser && currentUser.role === 'ADMIN'">
              <div class="flex items-center gap-1">
                <button @click="switchTab('dashboard')" :class="activeTab === 'dashboard' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="layout-dashboard" class="w-4 h-4"></i><span>Rekap & Hasil Akhir</span>
                </button>
                <button @click="switchTab('employees')" :class="activeTab === 'employees' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="users" class="w-4 h-4"></i><span>Data Karyawan</span>
                  <span class="px-1.5 py-0.2 text-[10px] rounded-full bg-emerald-100 text-emerald-800 font-bold" x-text="employees.length"></span>
                </button>
                <button @click="switchTab('supervisors')" :class="activeTab === 'supervisors' ? 'bg-white text-blue-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="user-cog" class="w-4 h-4"></i><span>Akun & Akses Kepala Bagian</span>
                  <span class="px-1.5 py-0.2 text-[10px] rounded-full bg-blue-100 text-blue-800 font-bold" x-text="supervisors.length"></span>
                </button>
                <button @click="switchTab('absen')" :class="activeTab === 'absen' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="calendar-check" class="w-4 h-4"></i><span>1. Absen</span>
                </button>
                <button @click="switchTab('kinerja')" :class="activeTab === 'kinerja' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="target" class="w-4 h-4"></i><span>2. Kinerja (Jobdesc)</span>
                </button>
                <button @click="switchTab('sp')" :class="activeTab === 'sp' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="alert-octagon" class="w-4 h-4"></i><span>3. SP (HRD)</span>
                </button>
                <button @click="switchTab('tahsin')" :class="activeTab === 'tahsin' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="book-open" class="w-4 h-4"></i><span>4. Tahsin</span>
                </button>
                <button @click="switchTab('director')" :class="activeTab === 'director' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="briefcase" class="w-4 h-4"></i><span>5. Kebijakan Direktur</span>
                </button>
                <button @click="switchTab('settings')" :class="activeTab === 'settings' ? 'bg-white text-emerald-700 shadow-sm font-semibold' : 'text-slate-600 hover:text-slate-900'" class="flex items-center gap-1 px-3 py-2 rounded-lg text-xs transition whitespace-nowrap">
                  <i data-lucide="sliders" class="w-4 h-4"></i><span>Pengaturan</span>
                </button>
              </div>
            </template>
 
            <!-- MENU KEPALA BAGIAN (HANYA PENILAIAN KINERJA TIMNYA) -->
            <template x-if="currentUser && currentUser.role === 'SUPERVISOR'">
              <div class="flex items-center gap-2 px-2 py-1">
                <button @click="switchTab('kinerja')" class="bg-white text-blue-700 shadow-sm font-bold flex items-center gap-1.5 px-3 py-1.5 rounded-lg text-xs">
                  <i data-lucide="clipboard-check" class="w-4 h-4"></i>
                  <span>Penilaian Kinerja Tim (<span x-text="roleFilteredEmployees.length"></span> Karyawan)</span>
                </button>
                <span class="text-xs text-slate-500 hidden sm:inline">• Anda login sebagai Kepala Bagian (<strong x-text="currentUser.department"></strong>). Hanya menampilkan anggota tim yang ditugaskan kepada Anda.</span>
              </div>
            </template>
          </nav>
        </div>
      </div>
    </header>
 
    <!-- Main Container -->
    <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-6 space-y-6">
 
      <!-- =================================================================== -->
      <!-- TAB BARU: AKUN & AKSES KEPALA BAGIAN (KHUSUS ADMIN)                 -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'supervisors' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6" style="display: none;">
        <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div>
            <h2 class="text-lg font-bold text-slate-900">Manajemen Akun & Mapping Penilai (Kepala Bagian)</h2>
            <p class="text-xs sm:text-sm text-slate-500">Buat akun login untuk masing-masing Kepala Bagian dan pilih karyawan mana saja yang wajib mereka nilai kinerjanya.</p>
          </div>
          <button @click="openAddSupervisorModal()" class="px-4 py-2.5 bg-blue-600 hover:bg-blue-700 text-white text-xs sm:text-sm font-semibold rounded-xl shadow-sm transition flex items-center gap-2">
            <i data-lucide="user-plus" class="w-4 h-4"></i><span>+ Tambah Akun Kepala Bagian</span>
          </button>
        </div>
 
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
          <template x-for="sup in supervisors" :key="sup.id">
            <div class="bg-white rounded-2xl border border-slate-200 shadow-sm p-5 flex flex-col justify-between space-y-4">
              <div class="space-y-3">
                <div class="flex items-start justify-between">
                  <div>
                    <span class="px-2.5 py-0.5 text-[11px] font-bold rounded-full bg-blue-100 text-blue-800" x-text="sup.department"></span>
                    <h3 class="text-base font-bold text-slate-900 mt-1.5" x-text="sup.name"></h3>
                  </div>
                  <div class="flex items-center gap-1">
                    <button @click="openEditSupervisorModal(sup)" class="p-1.5 text-slate-500 hover:text-blue-600 hover:bg-blue-50 rounded-lg" title="Edit Akun"><i data-lucide="edit-2" class="w-4 h-4"></i></button>
                    <button @click="deleteSupervisor(sup.id)" class="p-1.5 text-slate-500 hover:text-rose-600 hover:bg-rose-50 rounded-lg" title="Hapus Akun"><i data-lucide="trash-2" class="w-4 h-4"></i></button>
                  </div>
                </div>
 
                <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 text-xs space-y-1">
                  <div class="flex justify-between">
                    <span class="text-slate-500">Username Login:</span>
                    <span class="font-mono font-bold text-slate-800" x-text="sup.username"></span>
                  </div>
                  <div class="flex justify-between">
                    <span class="text-slate-500">Password / PIN:</span>
                    <span class="font-mono font-bold text-slate-800" x-text="sup.password"></span>
                  </div>
                </div>
 
                <div>
                  <div class="text-xs font-bold text-slate-700 mb-1.5 flex items-center justify-between">
                    <span>Karyawan yang Dinilai:</span>
                    <span class="px-2 py-0.5 rounded-full bg-emerald-100 text-emerald-800 text-[11px]" x-text="getValidAssignedEmpIds(sup).length + ' Orang'"></span>
                  </div>
                  <div class="max-h-28 overflow-y-auto border rounded-xl p-2 bg-slate-50/60 space-y-1">
                    <template x-if="getValidAssignedEmpIds(sup).length === 0">
                      <p class="text-[11px] text-slate-400 italic text-center py-2">Belum ada karyawan dipilih.</p>
                    </template>
                    <template x-for="empId in getValidAssignedEmpIds(sup)" :key="empId">
                      <div class="text-xs text-slate-700 flex items-center justify-between bg-white px-2 py-1 rounded border border-slate-100">
                        <span class="truncate font-medium" x-text="getEmployeeNameById(empId)"></span>
                      </div>
                    </template>
                  </div>
                </div>
              </div>
 
              <button @click="openAssignModal(sup)" class="w-full py-2.5 bg-emerald-50 hover:bg-emerald-100 text-emerald-800 border border-emerald-200 text-xs font-bold rounded-xl transition flex items-center justify-center gap-1.5">
                <i data-lucide="check-square" class="w-4 h-4"></i><span>Atur Daftar Karyawan yang Dinilai</span>
              </button>
            </div>
          </template>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 1: DATA KARYAWAN (KHUSUS ADMIN)                                 -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'employees' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6" style="display: none;">
        <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div>
            <h2 class="text-lg font-bold text-slate-900">Manajemen Master Data Karyawan (PT MKK & CV MGM)</h2>
            <p class="text-xs sm:text-sm text-slate-500">Kelola daftar karyawan, jabatan, departemen, dan gaji pokok.</p>
          </div>
          <div class="flex flex-wrap items-center gap-2.5">
            <button @click="openAddEmployeeModal()" class="px-4 py-2.5 bg-emerald-600 hover:bg-emerald-700 text-white text-xs sm:text-sm font-semibold rounded-xl shadow-sm transition flex items-center gap-2">
              <i data-lucide="user-plus" class="w-4 h-4"></i><span>+ Tambah Karyawan</span>
            </button>
            <label class="px-4 py-2.5 bg-blue-600 hover:bg-blue-700 text-white text-xs sm:text-sm font-semibold rounded-xl shadow-sm transition flex items-center gap-2 cursor-pointer">
              <i data-lucide="upload" class="w-4 h-4"></i><span>Upload Massal File (.xlsx / .csv)</span>
              <input type="file" accept=".xlsx, .xls, .csv" @change="handleFileUpload($event)" class="hidden">
            </label>
            <button @click="downloadTemplate('employees')" class="px-3.5 py-2.5 bg-slate-100 hover:bg-slate-200 text-slate-700 text-xs sm:text-sm font-semibold rounded-xl transition flex items-center gap-2">
              <i data-lucide="file-spreadsheet" class="w-4 h-4"></i><span>Template Excel</span>
            </button>
            <button @click="openResetDummyModal()" class="px-4 py-2.5 bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 text-xs sm:text-sm font-semibold rounded-xl transition flex items-center gap-2">
              <i data-lucide="trash-2" class="w-4 h-4"></i><span>Kosongkan Data</span>
            </button>
          </div>
        </div>
 
        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm grid grid-cols-1 sm:grid-cols-3 gap-4">
          <div class="sm:col-span-2">
            <label class="block text-xs font-semibold text-slate-500 mb-1">Cari Karyawan (Nama / NIK / Jabatan)</label>
            <div class="relative">
              <input type="text" x-model="globalFilter.search" placeholder="Ketik kata kunci..." class="w-full pl-9 pr-3 py-2 text-sm bg-slate-50 border border-slate-300 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:outline-none">
              <i data-lucide="search" class="w-4 h-4 text-slate-400 absolute left-3 top-2.5"></i>
            </div>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Unit Perusahaan</label>
            <select x-model="globalFilter.unit" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl focus:ring-2 focus:ring-emerald-500">
              <option value="ALL">Semua Unit (PT & CV)</option>
              <option value="PT">PT Medika Kesehatan Kerja (PT MKK)</option>
              <option value="CV">CV Medika Group Mandiri (CV MGM)</option>
            </select>
          </div>
        </div>
 
        <div class="bg-white rounded-2xl border border-slate-200 shadow-sm overflow-hidden">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-sm">
              <thead>
                <tr class="bg-slate-100 border-b border-slate-200 text-xs font-bold text-slate-600 uppercase">
                  <th class="py-3 px-4 w-12 text-center">No</th>
                  <th class="py-3 px-4">NIK</th>
                  <th class="py-3 px-4">Nama Lengkap</th>
                  <th class="py-3 px-4">Unit</th>
                  <th class="py-3 px-4">Organization / Departemen</th>
                  <th class="py-3 px-4">Jabatan</th>
                  <th class="py-3 px-4 text-right">Gaji Pokok</th>
                  <th class="py-3 px-4 text-center">Aksi</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200">
                <template x-for="(emp, idx) in filteredMasterEmployees" :key="emp.id">
                  <tr class="hover:bg-slate-50">
                    <td class="py-3 px-4 text-center text-xs text-slate-500" x-text="idx + 1"></td>
                    <td class="py-3 px-4 font-mono text-xs font-semibold text-slate-700" x-text="emp.nik"></td>
                    <td class="py-3 px-4 font-bold text-slate-900" x-text="emp.name"></td>
                    <td class="py-3 px-4">
                      <span class="px-2.5 py-0.5 text-[11px] font-extrabold rounded-md" :class="emp.unit === 'PT' ? 'bg-blue-100 text-blue-800' : 'bg-rose-100 text-rose-800'" x-text="emp.unit === 'PT' ? 'PT MKK' : 'CV MGM'"></span>
                    </td>
                    <td class="py-3 px-4 text-slate-700" x-text="emp.department"></td>
                    <td class="py-3 px-4 text-slate-600" x-text="emp.position || '-'"></td>
                    <td class="py-3 px-4 text-right font-semibold text-slate-800" x-text="emp.baseSalary > 0 ? formatRupiah(emp.baseSalary) : '-'"></td>
                    <td class="py-3 px-4 text-center">
                      <div class="flex items-center justify-center gap-1.5">
                        <button @click="openEditEmployeeModal(emp)" class="px-2.5 py-1 text-xs font-semibold text-emerald-700 bg-emerald-50 hover:bg-emerald-100 rounded-lg">Edit</button>
                        <button @click="confirmDeleteEmployee(emp)" class="p-1 text-rose-600 hover:bg-rose-50 rounded-lg"><i data-lucide="trash-2" class="w-4 h-4"></i></button>
                      </div>
                    </td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 2: ABSEN (KHUSUS ADMIN)                                         -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'absen' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6" style="display: none;">
        <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div class="space-y-1">
            <h2 class="text-lg font-bold text-slate-900">1. Komponen Absen (Sumber: Rekap Manual HR)</h2>
            <p class="text-xs text-slate-500">
              Maksimal Poin Absen: <strong class="text-emerald-700" x-text="settings.weights.absenMax + ' Poin'"></strong>.
              Potongan Terlambat: <strong class="text-amber-700" x-text="getLateRulesSummary()"></strong>.
              Potongan Alpha: <strong class="text-rose-600" x-text="'-' + (settings.absenPenaltyAlpha || 0) + ' pt / hari'"></strong>.
            </p>
          </div>
        </div>
 
        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm grid grid-cols-1 sm:grid-cols-3 gap-4">
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter PT / CV</label>
            <select x-model="globalFilter.unit" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Unit (PT & CV)</option>
              <option value="PT">PT Medika Kesehatan Kerja (PT MKK)</option>
              <option value="CV">CV Medika Group Mandiri (CV MGM)</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Organization</label>
            <select x-model="globalFilter.dept" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Organization</option>
              <template x-for="d in uniqueDepartments" :key="d">
                <option :value="d" x-text="d"></option>
              </template>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Search</label>
            <input type="text" x-model="globalFilter.search" placeholder="Cari nama / NIK..." class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
          </div>
        </div>
 
        <div class="bg-white rounded-2xl border border-slate-200 shadow-sm overflow-hidden">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-sm">
              <thead>
                <tr class="bg-slate-100 border-b border-slate-200 text-xs font-bold text-slate-600 uppercase">
                  <th class="py-3.5 px-4">Karyawan</th>
                  <th class="py-3.5 px-4">Unit & Organization</th>
                  <th class="py-3.5 px-4 text-center">Jumlah Terlambat (Hari)</th>
                  <th class="py-3.5 px-4 text-center">Jumlah Alpha (Hari)</th>
                  <th class="py-3.5 px-4 text-center">Total Potongan</th>
                  <th class="py-3.5 px-4 text-right bg-slate-200/50">Poin Absen</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200">
                <template x-for="emp in filteredEmployees" :key="emp.id">
                  <tr class="hover:bg-slate-50">
                    <td class="py-3.5 px-4 font-bold text-slate-900" x-text="emp.name + ' (' + emp.nik + ')'"></td>
                    <td class="py-3.5 px-4 text-xs text-slate-600"><span class="font-bold" :class="emp.unit==='PT'?'text-blue-700':'text-rose-700'" x-text="emp.unit"></span> - <span x-text="emp.department"></span></td>
                    <td class="py-3.5 px-4 text-center">
                      <input type="number" min="0" x-model.number="emp.absenLate" @change="saveToStorage()" class="w-24 p-2 text-center text-sm font-bold border rounded-lg">
                      <div class="text-[11px] text-amber-700 font-semibold mt-1" x-text="'Potong ' + formatNum(calcLatePenalty(emp.absenLate)) + ' pt'"></div>
                    </td>
                    <td class="py-3.5 px-4 text-center">
                      <input type="number" min="0" x-model.number="emp.absenAlpha" @change="saveToStorage()" class="w-24 p-2 text-center text-sm font-bold border rounded-lg">
                      <div class="text-[11px] text-rose-600 font-semibold mt-1" x-text="'Potong ' + formatNum(calcAlphaPenalty(emp.absenAlpha)) + ' pt'"></div>
                    </td>
                    <td class="py-3.5 px-4 text-center font-bold text-rose-600" x-text="'-' + formatNum(calcLatePenalty(emp.absenLate) + calcAlphaPenalty(emp.absenAlpha)) + ' pt'"></td>
                    <td class="py-3.5 px-4 text-right font-extrabold text-emerald-700 bg-slate-50" x-text="formatNum(calcAbsenPoints(emp)) + ' pt'"></td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 3: KINERJA (ADMIN & KEPALA BAGIAN - TERFILTER OTOMATIS)         -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'kinerja'" class="space-y-6" style="display: none;">
        <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div>
            <div class="flex items-center gap-2">
              <h2 class="text-lg font-bold text-slate-900" x-text="currentUser && currentUser.role === 'ADMIN' ? '2. Komponen Kinerja (Custom Jobdesc & Bobot per Karyawan)' : 'Penilaian Kinerja Karyawan — ' + currentUser.department"></h2>
              <span x-show="currentUser && currentUser.role === 'SUPERVISOR'" class="px-2.5 py-0.5 text-xs font-bold rounded-full bg-blue-100 text-blue-800">Mode Kepala Bagian</span>
            </div>
            <p class="text-xs text-slate-500 mt-0.5" x-text="currentUser && currentUser.role === 'ADMIN' ? 'Admin dapat mengatur item jobdesc, bobot (%), serta menginput/memantau nilai kinerja semua karyawan.' : 'Silakan klik tombol Nilai Kinerja pada masing-masing anggota tim Anda di bawah ini untuk memberikan skor penilaian (0 - 100) pada setiap item tugas.'"></p>
          </div>
        </div>
 
        <!-- Filter Panel Kinerja -->
        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm grid grid-cols-1 sm:grid-cols-3 gap-4">
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter PT / CV</label>
            <select x-model="globalFilter.unit" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Unit (PT & CV)</option>
              <option value="PT">PT Medika Kesehatan Kerja (PT MKK)</option>
              <option value="CV">CV Medika Group Mandiri (CV MGM)</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Organization</label>
            <select x-model="globalFilter.dept" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Organization</option>
              <template x-for="d in uniqueDepartments" :key="d">
                <option :value="d" x-text="d"></option>
              </template>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Cari Karyawan</label>
            <input type="text" x-model="globalFilter.search" placeholder="Cari nama / NIK..." class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
          </div>
        </div>
 
        <!-- Peringatan jika Kepala Bagian belum di-assign karyawan -->
        <div x-show="currentUser && currentUser.role === 'SUPERVISOR' && roleFilteredEmployees.length === 0" class="bg-amber-50 border border-amber-200 p-6 rounded-2xl text-center space-y-2">
          <i data-lucide="users" class="w-8 h-8 text-amber-600 mx-auto"></i>
          <h3 class="text-sm font-bold text-amber-900">Belum Ada Karyawan yang Ditugaskan</h3>
          <p class="text-xs text-amber-800 max-w-md mx-auto">Akun Kepala Bagian Anda belum memiliki daftar karyawan yang harus dinilai. Silakan hubungi Admin / HRD untuk mengatur daftar tim Anda.</p>
        </div>
 
        <!-- Tabel Daftar Karyawan untuk Kinerja -->
        <div x-show="roleFilteredEmployees.length > 0" class="bg-white rounded-2xl border border-slate-200 shadow-sm overflow-hidden">
          <div class="p-4 border-b border-slate-100 flex items-center justify-between">
            <h3 class="text-sm font-bold text-slate-900">Daftar Karyawan untuk Dinilai Kinerjanya</h3>
            <span class="text-xs text-slate-500 font-semibold" x-text="roleFilteredEmployees.length + ' karyawan'"></span>
          </div>
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-sm">
              <thead>
                <tr class="bg-slate-100 border-b border-slate-200 text-xs font-bold text-slate-600 uppercase">
                  <th class="py-3 px-4">Karyawan & Jabatan</th>
                  <th class="py-3 px-4">Unit & Organization</th>
                  <th class="py-3 px-4 text-center">Jumlah Item Jobdesc</th>
                  <th class="py-3 px-4 text-center">Total Bobot (%)</th>
                  <th class="py-3 px-4 text-right bg-slate-200/50">Skor Kinerja Diperoleh</th>
                  <th class="py-3 px-4 text-center">Aksi Penilaian</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200">
                <template x-for="emp in roleFilteredEmployees" :key="emp.id">
                  <tr class="hover:bg-slate-50">
                    <td class="py-3.5 px-4">
                      <div class="font-bold text-slate-900" x-text="emp.name"></div>
                      <div class="text-xs text-slate-500" x-text="emp.nik + ' • ' + (emp.position || 'Staff')"></div>
                    </td>
                    <td class="py-3.5 px-4 text-xs text-slate-600">
                      <span class="font-bold" :class="emp.unit==='PT'?'text-blue-700':'text-rose-700'" x-text="emp.unit"></span> - <span x-text="emp.department"></span>
                    </td>
                    <td class="py-3.5 px-4 text-center font-semibold text-slate-700" x-text="(emp.jobdesItems || []).length + ' Item'"></td>
                    <td class="py-3.5 px-4 text-center">
                      <span class="px-2 py-1 text-xs font-bold rounded" :class="getTotalJobdesWeight(emp) === 1 ? 'bg-emerald-100 text-emerald-800' : 'bg-amber-100 text-amber-800'" x-text="(getTotalJobdesWeight(emp) * 100) + '%'"></span>
                    </td>
                    <td class="py-3.5 px-4 text-right font-extrabold text-emerald-700 bg-slate-50" x-text="formatNum(calcKinerjaPoints(emp)) + ' / ' + settings.weights.kinerjaMax + ' pt'"></td>
                    <td class="py-3.5 px-4 text-center">
                      <button @click="openJobdescModal(emp)" class="px-3.5 py-2 bg-blue-600 hover:bg-blue-700 text-white text-xs font-bold rounded-xl shadow-sm transition flex items-center gap-1.5 mx-auto">
                        <i data-lucide="edit-3" class="w-3.5 h-3.5"></i>
                        <span x-text="currentUser && currentUser.role === 'ADMIN' ? 'Atur & Nilai Jobdesc' : 'Input Nilai Kinerja'"></span>
                      </button>
                    </td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 4: SP (KHUSUS ADMIN)                                            -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'sp' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6" style="display: none;">
        <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div>
            <h2 class="text-lg font-bold text-slate-900">3. Komponen Surat Peringatan / SP (Sumber: Data HRD)</h2>
            <p class="text-xs text-slate-500">Pengurangan poin: SP1 (<span x-text="settings.spDeductions.SP1"></span> pt), SP2 (<span x-text="settings.spDeductions.SP2"></span> pt), SP3 (<span x-text="settings.spDeductions.SP3"></span> pt).</p>
          </div>
        </div>
 
        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm grid grid-cols-1 sm:grid-cols-3 gap-4">
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter PT / CV</label>
            <select x-model="globalFilter.unit" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Unit (PT & CV)</option>
              <option value="PT">PT Medika Kesehatan Kerja (PT MKK)</option>
              <option value="CV">CV Medika Group Mandiri (CV MGM)</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Organization</label>
            <select x-model="globalFilter.dept" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Organization</option>
              <template x-for="d in uniqueDepartments" :key="d">
                <option :value="d" x-text="d"></option>
              </template>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Search</label>
            <input type="text" x-model="globalFilter.search" placeholder="Cari nama / NIK..." class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
          </div>
        </div>
 
        <div class="bg-white rounded-2xl border border-slate-200 shadow-sm overflow-hidden">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-sm">
              <thead>
                <tr class="bg-slate-100 border-b border-slate-200 text-xs font-bold text-slate-600 uppercase">
                  <th class="py-3.5 px-4">Karyawan</th>
                  <th class="py-3.5 px-4">Unit & Organization</th>
                  <th class="py-3.5 px-4 text-center">Status Surat Peringatan (SP)</th>
                  <th class="py-3.5 px-4 text-right bg-slate-200/50">Poin Penyesuaian SP</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200">
                <template x-for="emp in filteredEmployees" :key="emp.id">
                  <tr class="hover:bg-slate-50">
                    <td class="py-3.5 px-4 font-bold text-slate-900" x-text="emp.name + ' (' + emp.nik + ')'"></td>
                    <td class="py-3.5 px-4 text-xs text-slate-600"><span class="font-bold" :class="emp.unit==='PT'?'text-blue-700':'text-rose-700'" x-text="emp.unit"></span> - <span x-text="emp.department"></span></td>
                    <td class="py-3.5 px-4 text-center">
                      <select x-model="emp.spStatus" @change="saveToStorage()" class="p-2 text-sm font-semibold border rounded-lg bg-white">
                        <option value="NONE">Tidak Ada SP (0 pt)</option>
                        <option value="SP1" x-text="'SP 1 (' + settings.spDeductions.SP1 + ' pt)'"></option>
                        <option value="SP2" x-text="'SP 2 (' + settings.spDeductions.SP2 + ' pt)'"></option>
                        <option value="SP3" x-text="'SP 3 (' + settings.spDeductions.SP3 + ' pt)'"></option>
                      </select>
                    </td>
                    <td class="py-3.5 px-4 text-right font-extrabold text-rose-600 bg-slate-50" x-text="calcSpPoints(emp) + ' pt'"></td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 5: TAHSIN (KHUSUS ADMIN)                                        -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'tahsin' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6" style="display: none;">
        <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div>
            <h2 class="text-lg font-bold text-slate-900">4. Komponen Tahsin (Sumber: Mentor / Pengajar Tahsin)</h2>
            <p class="text-xs text-slate-500">Bobot Maksimal Tahsin: <strong class="text-emerald-700" x-text="settings.weights.tahsinMax + ' Poin'"></strong> (Skala Nilai 0 - 100).</p>
          </div>
        </div>
 
        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm grid grid-cols-1 sm:grid-cols-3 gap-4">
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter PT / CV</label>
            <select x-model="globalFilter.unit" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Unit (PT & CV)</option>
              <option value="PT">PT Medika Kesehatan Kerja (PT MKK)</option>
              <option value="CV">CV Medika Group Mandiri (CV MGM)</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Organization</label>
            <select x-model="globalFilter.dept" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Organization</option>
              <template x-for="d in uniqueDepartments" :key="d">
                <option :value="d" x-text="d"></option>
              </template>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Search</label>
            <input type="text" x-model="globalFilter.search" placeholder="Cari nama / NIK..." class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
          </div>
        </div>
 
        <div class="bg-white rounded-2xl border border-slate-200 shadow-sm overflow-hidden">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-sm">
              <thead>
                <tr class="bg-slate-100 border-b border-slate-200 text-xs font-bold text-slate-600 uppercase">
                  <th class="py-3.5 px-4">Karyawan</th>
                  <th class="py-3.5 px-4">Unit & Organization</th>
                  <th class="py-3.5 px-4 text-center">Nilai Tahsin (0 - 100)</th>
                  <th class="py-3.5 px-4 text-right bg-slate-200/50">Poin Tahsin Diperoleh</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200">
                <template x-for="emp in filteredEmployees" :key="emp.id">
                  <tr class="hover:bg-slate-50">
                    <td class="py-3.5 px-4 font-bold text-slate-900" x-text="emp.name + ' (' + emp.nik + ')'"></td>
                    <td class="py-3.5 px-4 text-xs text-slate-600"><span class="font-bold" :class="emp.unit==='PT'?'text-blue-700':'text-rose-700'" x-text="emp.unit"></span> - <span x-text="emp.department"></span></td>
                    <td class="py-3.5 px-4 text-center"><input type="number" min="0" max="100" x-model.number="emp.tahsinScore" @change="saveToStorage()" class="w-32 p-2 text-center text-sm font-bold border rounded-lg"></td>
                    <td class="py-3.5 px-4 text-right font-extrabold text-emerald-700 bg-slate-50" x-text="formatNum(calcTahsinPoints(emp)) + ' pt'"></td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 6: KEBIJAKAN DIREKTUR (KHUSUS ADMIN)                            -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'director' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6" style="display: none;">
        <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div>
            <h2 class="text-lg font-bold text-slate-900">5. Komponen Kebijakan Direktur / Lain-Lain</h2>
            <p class="text-xs text-slate-500">Penyesuaian poin tambahan/pengurangan oleh Direktur.</p>
          </div>
        </div>
 
        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm grid grid-cols-1 sm:grid-cols-3 gap-4">
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter PT / CV</label>
            <select x-model="globalFilter.unit" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Unit (PT & CV)</option>
              <option value="PT">PT Medika Kesehatan Kerja (PT MKK)</option>
              <option value="CV">CV Medika Group Mandiri (CV MGM)</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Organization</label>
            <select x-model="globalFilter.dept" class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
              <option value="ALL">Semua Organization</option>
              <template x-for="d in uniqueDepartments" :key="d">
                <option :value="d" x-text="d"></option>
              </template>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Search</label>
            <input type="text" x-model="globalFilter.search" placeholder="Cari nama / NIK..." class="w-full p-2 text-sm bg-slate-50 border border-slate-300 rounded-xl">
          </div>
        </div>
 
        <div class="bg-white rounded-2xl border border-slate-200 shadow-sm overflow-hidden">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-sm">
              <thead>
                <tr class="bg-slate-100 border-b border-slate-200 text-xs font-bold text-slate-600 uppercase">
                  <th class="py-3.5 px-4">Karyawan</th>
                  <th class="py-3.5 px-3 text-center">Absen</th>
                  <th class="py-3.5 px-3 text-center">Kinerja</th>
                  <th class="py-3.5 px-3 text-center">SP</th>
                  <th class="py-3.5 px-3 text-center">Tahsin</th>
                  <th class="py-3.5 px-3 text-center bg-blue-50/70 text-blue-900">Total Sementara</th>
                  <th class="py-3.5 px-4 text-center bg-emerald-50/70 text-emerald-900">Poin Lain-Lain (+/-)</th>
                  <th class="py-3.5 px-4 bg-emerald-50/70 text-emerald-900">Catatan / Alasan</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200">
                <template x-for="emp in filteredEmployees" :key="emp.id">
                  <tr class="hover:bg-slate-50">
                    <td class="py-3.5 px-4">
                      <div class="font-bold text-slate-900" x-text="emp.name"></div>
                      <div class="text-xs text-slate-500" x-text="emp.nik + ' • ' + emp.department"></div>
                    </td>
                    <td class="py-3.5 px-3 text-center font-semibold text-slate-700" x-text="formatNum(calcAbsenPoints(emp))"></td>
                    <td class="py-3.5 px-3 text-center font-semibold text-slate-700" x-text="formatNum(calcKinerjaPoints(emp))"></td>
                    <td class="py-3.5 px-3 text-center font-semibold text-rose-600" x-text="calcSpPoints(emp)"></td>
                    <td class="py-3.5 px-3 text-center font-semibold text-slate-700" x-text="formatNum(calcTahsinPoints(emp))"></td>
                    <td class="py-3.5 px-3 text-center font-extrabold text-blue-700 bg-blue-50/40" x-text="formatNum(calcAbsenPoints(emp) + calcKinerjaPoints(emp) + calcSpPoints(emp) + calcTahsinPoints(emp))"></td>
                    <td class="py-3.5 px-4 text-center bg-emerald-50/30">
                      <input type="number" step="0.5" x-model.number="emp.directorAdj" @change="saveToStorage()" placeholder="0" class="w-28 p-2 text-center text-sm font-extrabold text-emerald-800 border rounded-lg bg-white">
                    </td>
                    <td class="py-3.5 px-4 bg-emerald-50/30">
                      <input type="text" x-model="emp.directorNote" @change="saveToStorage()" placeholder="Alasan kebijakan..." class="w-full p-2 text-sm border rounded-lg bg-white">
                    </td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 7: REKAP & HASIL AKHIR (DASHBOARD - KHUSUS ADMIN)               -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'dashboard' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6">
        <div class="bg-gradient-to-r from-slate-900 via-slate-800 to-emerald-950 text-white rounded-2xl p-5 sm:p-6 shadow-md flex flex-col lg:flex-row lg:items-center justify-between gap-4">
          <div class="space-y-1">
            <div class="inline-flex items-center gap-1.5 text-xs font-semibold uppercase tracking-wider text-emerald-300 bg-emerald-900/60 px-2.5 py-1 rounded-lg border border-emerald-700/50">
              <i data-lucide="calendar-check" class="w-3.5 h-3.5"></i>
              <span>Parameter Penilaian Tahun <span x-text="settings.year"></span></span>
            </div>
            <h2 class="text-xl sm:text-2xl font-bold">Ringkasan Evaluasi Kinerja & Penyesuaian Gaji</h2>
            <div class="flex flex-wrap items-center gap-2 text-xs sm:text-sm text-slate-300 pt-1">
              <span>Skema Range Aktif:</span>
              <template x-for="(rule, rIdx) in settings.scoreRules" :key="rIdx">
                <span class="px-2 py-0.5 rounded bg-white/10 text-emerald-200 border text-xs">
                  <strong x-text="rule.minScore + ' - ' + rule.maxScore"></strong>: <span x-text="rule.category"></span> (<span x-text="'+' + rule.raisePercent + '%'"></span>)
                </span>
              </template>
            </div>
          </div>
          <div class="flex flex-wrap items-center gap-2 no-print">
            <button @click="exportExcel()" class="px-4 py-2.5 bg-emerald-600 hover:bg-emerald-700 text-white text-xs sm:text-sm font-semibold rounded-xl transition flex items-center gap-2 shadow-sm">
              <i data-lucide="file-spreadsheet" class="w-4 h-4"></i><span>Export Excel (.xlsx)</span>
            </button>
            <button @click="window.print()" class="px-4 py-2.5 bg-white/10 hover:bg-white/20 text-white border text-xs sm:text-sm font-semibold rounded-xl transition flex items-center gap-2">
              <i data-lucide="printer" class="w-4 h-4"></i><span>Cetak Laporan</span>
            </button>
          </div>
        </div>
 
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
          <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm flex items-center justify-between">
            <div>
              <p class="text-xs font-semibold text-slate-500 uppercase">Total Karyawan</p>
              <p class="text-2xl font-extrabold text-slate-900 mt-1" x-text="filteredEmployees.length + ' Orang'"></p>
              <p class="text-xs text-slate-400 mt-0.5" x-text="'PT: ' + countByUnit('PT') + ' | CV: ' + countByUnit('CV')"></p>
            </div>
            <div class="w-12 h-12 rounded-2xl bg-slate-100 text-slate-700 flex items-center justify-center"><i data-lucide="users" class="w-6 h-6"></i></div>
          </div>
 
          <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm flex items-center justify-between">
            <div>
              <p class="text-xs font-semibold text-emerald-600 uppercase">Masuk Kategori Baik / SB</p>
              <p class="text-2xl font-extrabold text-emerald-700 mt-1" x-text="goodCategoryCount + ' Orang'"></p>
              <p class="text-xs text-slate-500 mt-0.5" x-text="filteredEmployees.length ? Math.round((goodCategoryCount / filteredEmployees.length) * 100) + '%' : '0%'"></p>
            </div>
            <div class="w-12 h-12 rounded-2xl bg-emerald-50 text-emerald-600 flex items-center justify-center"><i data-lucide="check-circle-2" class="w-6 h-6"></i></div>
          </div>
 
          <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm flex items-center justify-between">
            <div>
              <p class="text-xs font-semibold text-rose-600 uppercase">Kategori Cukup / Kurang</p>
              <p class="text-2xl font-extrabold text-rose-600 mt-1" x-text="notGoodCategoryCount + ' Orang'"></p>
              <p class="text-xs text-slate-500 mt-0.5">Perlu evaluasi</p>
            </div>
            <div class="w-12 h-12 rounded-2xl bg-rose-50 text-rose-600 flex items-center justify-center"><i data-lucide="alert-circle" class="w-6 h-6"></i></div>
          </div>
 
          <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm flex items-center justify-between">
            <div>
              <p class="text-xs font-semibold text-blue-600 uppercase">Rata-Rata Kenaikan</p>
              <p class="text-2xl font-extrabold text-blue-700 mt-1" x-text="averageSalaryIncrease + '%'"></p>
              <p class="text-xs text-slate-500 mt-0.5" x-text="'Skor Rata: ' + averageTotalScore"></p>
            </div>
            <div class="w-12 h-12 rounded-2xl bg-blue-50 text-blue-600 flex items-center justify-center"><i data-lucide="trending-up" class="w-6 h-6"></i></div>
          </div>
        </div>
 
        <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm no-print grid grid-cols-1 sm:grid-cols-4 gap-4">
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Unit</label>
            <select x-model="globalFilter.unit" class="w-full p-2 text-sm bg-slate-50 border rounded-xl">
              <option value="ALL">Semua Unit (PT & CV)</option>
              <option value="PT">PT Medika Kesehatan Kerja (PT MKK)</option>
              <option value="CV">CV Medika Group Mandiri (CV MGM)</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Organization</label>
            <select x-model="globalFilter.dept" class="w-full p-2 text-sm bg-slate-50 border rounded-xl">
              <option value="ALL">Semua Organization</option>
              <template x-for="d in uniqueDepartments" :key="d">
                <option :value="d" x-text="d"></option>
              </template>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Filter Kategori</label>
            <select x-model="globalFilter.status" class="w-full p-2 text-sm bg-slate-50 border rounded-xl">
              <option value="ALL">Semua Kategori</option>
              <template x-for="cat in uniqueRuleCategories" :key="cat">
                <option :value="cat" x-text="cat"></option>
              </template>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-500 mb-1">Cari Karyawan</label>
            <input type="text" x-model="globalFilter.search" placeholder="Nama atau NIK..." class="w-full p-2 text-sm bg-slate-50 border rounded-xl">
          </div>
        </div>
 
        <div class="bg-white rounded-2xl border border-slate-200 shadow-sm overflow-hidden">
          <div class="p-5 border-b border-slate-200 flex items-center justify-between">
            <div>
              <h3 class="text-base font-bold text-slate-900">Rekapitulasi Akumulasi Nilai & Kenaikan Gaji</h3>
              <p class="text-xs text-slate-500">Kategori & kenaikan gaji disesuaikan otomatis berdasarkan aturan Range Nilai</p>
            </div>
            <div class="text-xs text-slate-500 font-semibold" x-text="filteredEmployees.length + ' data ditampilkan'"></div>
          </div>
 
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse">
              <thead>
                <tr class="bg-slate-100 border-b border-slate-200 text-[11px] font-bold text-slate-600 uppercase">
                  <th class="py-3.5 px-4">Karyawan & Unit</th>
                  <th class="py-3.5 px-3 text-center">1. Absen</th>
                  <th class="py-3.5 px-3 text-center">2. Kinerja (Jobdesc)</th>
                  <th class="py-3.5 px-3 text-center">3. SP</th>
                  <th class="py-3.5 px-3 text-center">4. Tahsin</th>
                  <th class="py-3.5 px-3 text-center">5. Lain-Lain</th>
                  <th class="py-3.5 px-3 text-center bg-slate-200/50 text-slate-900 font-extrabold">Total Skor</th>
                  <th class="py-3.5 px-4">Kategori & Range</th>
                  <th class="py-3.5 px-4 text-right">Kenaikan & Gaji Baru</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200 text-sm">
                <template x-for="emp in filteredEmployees" :key="emp.id">
                  <tr class="hover:bg-slate-50">
                    <td class="py-3.5 px-4">
                      <div class="flex items-start gap-2">
                        <span class="mt-0.5 px-2 py-0.5 text-[10px] font-extrabold rounded-md shrink-0" :class="emp.unit === 'PT' ? 'bg-blue-100 text-blue-800' : 'bg-rose-100 text-rose-800'" x-text="emp.unit"></span>
                        <div>
                          <div class="font-bold text-slate-900" x-text="emp.name"></div>
                          <div class="text-xs text-slate-500" x-text="emp.nik + ' • ' + emp.department"></div>
                        </div>
                      </div>
                    </td>
                    <td class="py-3.5 px-3 text-center font-semibold text-slate-700" x-text="formatNum(calcAbsenPoints(emp))"></td>
                    <td class="py-3.5 px-3 text-center font-semibold text-slate-700" x-text="formatNum(calcKinerjaPoints(emp))"></td>
                    <td class="py-3.5 px-3 text-center font-semibold text-rose-600" x-text="calcSpPoints(emp)"></td>
                    <td class="py-3.5 px-3 text-center font-semibold text-slate-700" x-text="formatNum(calcTahsinPoints(emp))"></td>
                    <td class="py-3.5 px-3 text-center font-bold" :class="Number(emp.directorAdj)>0?'text-emerald-700':(Number(emp.directorAdj)<0?'text-rose-600':'text-slate-400')" x-text="(Number(emp.directorAdj)>0?'+':'')+formatNum(emp.directorAdj)"></td>
                    <td class="py-3.5 px-3 text-center bg-slate-50"><span class="text-base font-extrabold text-slate-900" x-text="formatNum(calcTotalScore(emp))"></span></td>
                    <td class="py-3.5 px-4">
                      <div class="space-y-1">
                        <span class="inline-flex items-center gap-1.5 px-2.5 py-0.5 rounded-full text-xs font-bold" :class="getCategoryBadgeClass(emp)">
                          <span class="w-1.5 h-1.5 rounded-full" :class="getCategoryDotClass(emp)"></span>
                          <span x-text="getGradeLabel(emp)"></span>
                        </span>
                        <div class="text-[11px] font-medium text-slate-500" x-text="getMatchedRuleRangeText(emp)"></div>
                      </div>
                    </td>
                    <td class="py-3.5 px-4 text-right">
                      <div class="inline-flex items-center gap-1 px-2.5 py-1 rounded-lg font-extrabold text-sm" :class="getSalaryIncreaseRate(emp) > 0 ? 'bg-blue-50 text-blue-700' : 'bg-slate-100 text-slate-500'">
                        <span x-text="'+' + getSalaryIncreaseRate(emp) + '%'"></span>
                      </div>
                      <div x-show="emp.baseSalary > 0" class="text-[11px] text-slate-500 mt-1">
                        <div>Baru: <strong class="text-slate-700" x-text="formatRupiah(calcNewSalary(emp))"></strong></div>
                      </div>
                    </td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
        </div>
      </section>
 
      <!-- =================================================================== -->
      <!-- TAB 8: PENGATURAN (KHUSUS ADMIN)                                    -->
      <!-- =================================================================== -->
      <section x-show="activeTab === 'settings' && currentUser && currentUser.role === 'ADMIN'" class="space-y-6" style="display: none;">
        <div class="bg-amber-50 border border-amber-200 p-5 rounded-2xl flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4">
          <div>
            <h3 class="text-sm font-bold text-amber-900 flex items-center gap-2"><i data-lucide="shield-check" class="w-4 h-4"></i><span>Keamanan Data: Backup & Restore File (.json)</span></h3>
            <p class="text-xs text-amber-800 mt-0.5">Simpan cadangan seluruh data karyawan, skor, akun Kepala Bagian, dan pengaturan ke dalam file JSON.</p>
          </div>
          <div class="flex items-center gap-2.5">
            <button @click="exportDataJSON()" class="px-4 py-2 bg-amber-600 hover:bg-amber-700 text-white text-xs font-bold rounded-xl shadow-sm transition flex items-center gap-1.5">
              <i data-lucide="download" class="w-4 h-4"></i><span>Unduh Backup (.json)</span>
            </button>
            <label class="px-4 py-2 bg-indigo-600 hover:bg-indigo-700 text-white text-xs font-bold rounded-xl shadow-sm transition flex items-center gap-1.5 cursor-pointer">
              <i data-lucide="upload" class="w-4 h-4"></i><span>Pulihkan dari JSON</span>
              <input type="file" accept=".json" @change="importDataJSON($event)" class="hidden">
            </label>
          </div>
        </div>
 
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
          <div class="lg:col-span-7 bg-white p-6 rounded-2xl border border-slate-200 shadow-sm space-y-5">
            <div class="flex flex-wrap items-center justify-between gap-3 border-b border-slate-100 pb-4">
              <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-xl bg-blue-50 text-blue-600 flex items-center justify-center"><i data-lucide="sliders-horizontal" class="w-5 h-5"></i></div>
                <div>
                  <h2 class="text-base font-bold text-slate-900">Aturan Range Nilai, Kategori & Kenaikan Gaji</h2>
                  <p class="text-xs text-slate-500">Tentukan rentang nilai, kategori, dan persentase kenaikan</p>
                </div>
              </div>
              <button @click="addScoreRule()" class="px-3.5 py-2 bg-blue-600 hover:bg-blue-700 text-white text-xs font-semibold rounded-xl shadow-sm transition flex items-center gap-1.5">
                <i data-lucide="plus" class="w-3.5 h-3.5"></i><span>Tambah Range</span>
              </button>
            </div>
 
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-bold text-slate-600 mb-1">Tahun Periode Penilaian</label>
                <input type="number" x-model.number="settings.year" @change="saveToStorage()" class="w-full p-2.5 text-sm font-bold bg-slate-50 border rounded-xl">
              </div>
              <div>
                <label class="block text-xs font-bold text-slate-600 mb-1">Password Login Admin Utama</label>
                <input type="text" x-model="settings.adminPassword" @change="saveToStorage()" class="w-full p-2.5 text-sm font-mono font-bold bg-slate-50 border rounded-xl">
              </div>
            </div>
 
            <div class="space-y-2.5 pt-1">
              <template x-for="(rule, index) in settings.scoreRules" :key="index">
                <div class="p-3 rounded-xl border grid grid-cols-1 sm:grid-cols-12 gap-2.5 items-center" :class="getRuleRowStyle(rule.category)">
                  <div class="sm:col-span-2">
                    <input type="number" step="0.5" x-model.number="rule.minScore" @change="saveToStorage()" class="w-full p-2 text-center text-sm font-bold bg-white border rounded-lg">
                  </div>
                  <div class="sm:col-span-2">
                    <input type="number" step="0.5" x-model.number="rule.maxScore" @change="saveToStorage()" class="w-full p-2 text-center text-sm font-bold bg-white border rounded-lg">
                  </div>
                  <div class="sm:col-span-5">
                    <select x-model="rule.category" @change="saveToStorage()" class="w-full p-2 text-sm font-bold bg-white border rounded-lg">
                      <template x-for="opt in categoryOptions" :key="opt">
                        <option :value="opt" x-text="opt"></option>
                      </template>
                    </select>
                  </div>
                  <div class="sm:col-span-2">
                    <div class="relative">
                      <input type="number" step="0.5" x-model.number="rule.raisePercent" @change="saveToStorage()" class="w-full p-2 pr-6 text-center text-sm font-extrabold bg-white border rounded-lg">
                      <span class="absolute right-2 top-2 text-xs font-bold text-slate-400">%</span>
                    </div>
                  </div>
                  <div class="sm:col-span-1 flex justify-end sm:justify-center">
                    <button @click="removeScoreRule(index)" :disabled="settings.scoreRules.length <= 1" class="p-2 text-rose-600 hover:bg-rose-100 rounded-lg"><i data-lucide="trash-2" class="w-4 h-4"></i></button>
                  </div>
                </div>
              </template>
            </div>
          </div>
 
          <div class="lg:col-span-5 bg-white p-6 rounded-2xl border border-slate-200 shadow-sm space-y-5 flex flex-col justify-between">
            <div class="space-y-5">
              <div class="flex items-center gap-3 border-b border-slate-100 pb-4">
                <div class="w-10 h-10 rounded-xl bg-emerald-50 text-emerald-600 flex items-center justify-center"><i data-lucide="scale" class="w-5 h-5"></i></div>
                <div>
                  <h2 class="text-base font-bold text-slate-900">Bobot & Potongan Absensi</h2>
                  <p class="text-xs text-slate-500">Bobot komponen utama, tier terlambat & potongan alpha</p>
                </div>
              </div>
 
              <div class="grid grid-cols-3 gap-3">
                <div class="p-3 bg-slate-50 rounded-xl border">
                  <label class="block text-xs font-bold text-slate-700 mb-1">Maks. Absen</label>
                  <input type="number" x-model.number="settings.weights.absenMax" @change="saveToStorage()" class="w-full p-2 text-sm font-bold bg-white border rounded-lg">
                </div>
                <div class="p-3 bg-slate-50 rounded-xl border">
                  <label class="block text-xs font-bold text-slate-700 mb-1">Bobot Kinerja</label>
                  <input type="number" x-model.number="settings.weights.kinerjaMax" @change="saveToStorage()" class="w-full p-2 text-sm font-bold bg-white border rounded-lg">
                </div>
                <div class="p-3 bg-slate-50 rounded-xl border">
                  <label class="block text-xs font-bold text-slate-700 mb-1">Bobot Tahsin</label>
                  <input type="number" x-model.number="settings.weights.tahsinMax" @change="saveToStorage()" class="w-full p-2 text-sm font-bold bg-white border rounded-lg">
                </div>
              </div>

              <!-- Aturan Potongan Keterlambatan Bertingkat -->
              <div class="pt-3 border-t border-slate-100 space-y-2.5">
                <div class="flex items-center justify-between">
                  <span class="text-xs font-bold text-slate-700">Aturan Potongan Keterlambatan (Hari)</span>
                  <span class="text-[11px] text-slate-400">Kosongkan Maks = Tak terbatas</span>
                </div>

                <template x-for="(rule, lIdx) in settings.lateRules" :key="lIdx">
                  <div class="grid grid-cols-12 gap-2 items-center bg-slate-50 p-2 rounded-xl border text-xs">
                    <div class="col-span-3">
                      <label class="block text-[10px] text-slate-500">Min Hari</label>
                      <input type="number" min="0" x-model.number="rule.minDays" @change="saveToStorage()" class="w-full p-1.5 text-center font-bold bg-white border rounded-lg">
                    </div>
                    <div class="col-span-3">
                      <label class="block text-[10px] text-slate-500">Maks Hari</label>
                      <input type="number" min="0"
                             :value="rule.maxDays === null || rule.maxDays === undefined ? '' : rule.maxDays"
                             @input="rule.maxDays = ($event.target.value === '' ? null : Number($event.target.value)); saveToStorage()"
                             placeholder="∞"
                             class="w-full p-1.5 text-center font-bold bg-white border rounded-lg">
                    </div>
                    <div class="col-span-3">
                      <label class="block text-[10px] text-slate-500">Potong (pt)</label>
                      <input type="number" min="0" step="0.5" x-model.number="rule.penalty" @change="saveToStorage()" class="w-full p-1.5 text-center font-extrabold text-rose-600 bg-white border rounded-lg">
                    </div>
                    <div class="col-span-3 text-right pt-3">
                      <span class="text-[11px] font-semibold text-slate-600"
                            x-text="rule.maxDays === null || rule.maxDays === undefined ? (rule.minDays + '+ hr') : (rule.minDays === rule.maxDays ? (rule.minDays + ' hr') : (rule.minDays + '-' + rule.maxDays + ' hr'))"></span>
                    </div>
                  </div>
                </template>

                <div class="p-3 bg-rose-50/60 rounded-xl border border-rose-200/70 flex items-center justify-between gap-3">
                  <div>
                    <label class="block text-xs font-bold text-rose-900">Potongan Alpha per Hari</label>
                    <p class="text-[11px] text-rose-700">Dikalikan jumlah total hari alpha</p>
                  </div>
                  <input type="number" min="0" step="0.5" x-model.number="settings.absenPenaltyAlpha" @change="saveToStorage()" class="w-24 p-1.5 text-center text-sm font-extrabold text-rose-700 bg-white border border-rose-300 rounded-lg">
                </div>
              </div>
            </div>
 
            <div class="pt-4 border-t border-slate-100 flex justify-between items-center">
              <button @click="resetDefaultSettings()" class="px-4 py-2 text-xs font-semibold text-slate-600 bg-slate-100 hover:bg-slate-200 rounded-xl">Reset Default</button>
              <button @click="saveToStorage(); showToast('Pengaturan disimpan!', 'success')" class="px-5 py-2.5 text-xs font-semibold text-white bg-emerald-600 hover:bg-emerald-700 rounded-xl shadow">Simpan</button>
            </div>
          </div>
        </div>
      </section>
 
    </main>
 
    <!-- =================================================================== -->
    <!-- MODAL CUSTOM JOBDESC & BOBOT (ADMIN) / INPUT NILAI (KEPALA BAGIAN)  -->
    <!-- =================================================================== -->
    <div x-show="jobdescModal.open" style="display: none;" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-900/60 backdrop-blur-sm overflow-y-auto">
      <div @click.away="jobdescModal.open = false" class="bg-white w-full max-w-3xl rounded-2xl shadow-2xl border border-slate-200 overflow-hidden my-8">
        <div class="px-6 py-4 bg-emerald-900 text-white flex items-center justify-between">
          <div>
            <h3 class="text-base font-bold" x-text="(currentUser && currentUser.role === 'ADMIN' ? 'Custom Jobdesc & Bobot: ' : 'Penilaian Kinerja Karyawan: ') + (jobdescModal.emp ? jobdescModal.emp.name : '')"></h3>
            <p class="text-xs text-emerald-200" x-text="(jobdescModal.emp ? jobdescModal.emp.nik + ' • ' + (jobdescModal.emp.position || jobdescModal.emp.department) : '')"></p>
          </div>
          <button @click="jobdescModal.open = false" class="text-emerald-200 hover:text-white"><i data-lucide="x" class="w-5 h-5"></i></button>
        </div>
 
        <div class="p-6 space-y-4 max-h-[75vh] overflow-y-auto" x-data="{
          addItem() {
            if (!jobdescModal.emp.jobdesItems) jobdescModal.emp.jobdesItems = [];
            jobdescModal.emp.jobdesItems.push({ task: '', freq: '1 bulan 1x', weight: 0.1, score: 85 });
          },
          removeItem(idx) {
            jobdescModal.emp.jobdesItems.splice(idx, 1);
          }
        }">
          <!-- Toolbar khusus Admin (Salin & Tambah Item) -->
          <div x-show="currentUser && currentUser.role === 'ADMIN'" class="flex flex-col sm:flex-row items-start sm:items-center justify-between gap-3 bg-emerald-50 p-3.5 rounded-xl border border-emerald-200 text-xs text-emerald-900">
            <div>
              <span>Total Bobot Item: </span>
              <strong class="text-sm font-extrabold" :class="getTotalJobdesWeight(jobdescModal.emp) === 1 ? 'text-emerald-700' : 'text-amber-700'" x-text="(getTotalJobdesWeight(jobdescModal.emp) * 100) + '%'"></strong>
            </div>
            <div class="flex flex-wrap items-center gap-2 w-full sm:w-auto">
              <select x-model="copySourceEmpId" class="p-1.5 text-xs bg-white border rounded-lg font-semibold text-slate-700">
                <option value="">-- Salin Jobdesc dari Karyawan Lain --</option>
                <template x-for="oth in employees.filter(e => jobdescModal.emp && e.id !== jobdescModal.emp.id)" :key="oth.id">
                  <option :value="oth.id" x-text="oth.name + ' (' + (oth.position || oth.department) + ')'"></option>
                </template>
              </select>
              <button @click="copyJobdescFromOther()" class="px-3 py-1.5 bg-blue-600 hover:bg-blue-700 text-white font-semibold rounded-lg shadow-sm transition flex items-center gap-1 text-xs">
                <i data-lucide="copy" class="w-3.5 h-3.5"></i><span>Salin</span>
              </button>
              <button @click="addItem()" class="px-3 py-1.5 bg-emerald-600 hover:bg-emerald-700 text-white font-semibold rounded-lg shadow-sm transition flex items-center gap-1 text-xs">
                <i data-lucide="plus" class="w-3.5 h-3.5"></i><span>Tambah</span>
              </button>
            </div>
          </div>
 
          <!-- Info khusus Kepala Bagian -->
          <div x-show="currentUser && currentUser.role === 'SUPERVISOR'" class="bg-blue-50 p-3.5 rounded-xl border border-blue-200 text-xs text-blue-900 flex items-center justify-between">
            <span>Silakan isi kolom <strong>Nilai (0 - 100)</strong> sesuai pencapaian masing-masing item pekerjaan karyawan ini.</span>
            <span class="font-bold whitespace-nowrap ml-2" x-text="'Skor Konversi: ' + formatNum(calcKinerjaPoints(jobdescModal.emp)) + ' pt'"></span>
          </div>
 
          <div class="border rounded-xl overflow-hidden">
            <table class="w-full text-left text-sm">
              <thead class="bg-slate-100 text-xs uppercase text-slate-600">
                <tr>
                  <th class="p-3">Tanggung Jawab Utama (Jobdesc)</th>
                  <th class="p-3 w-32 text-center">Frekuensi</th>
                  <th class="p-3 w-28 text-center">Bobot</th>
                  <th class="p-3 w-28 text-center bg-blue-50 text-blue-900">Nilai (0-100)</th>
                  <th class="p-3 w-24 text-right">Konversi</th>
                  <th x-show="currentUser && currentUser.role === 'ADMIN'" class="p-3 w-12 text-center">Aksi</th>
                </tr>
              </thead>
              <tbody class="divide-y divide-slate-200">
                <template x-for="(item, idx) in (jobdescModal.emp ? jobdescModal.emp.jobdesItems : [])" :key="idx">
                  <tr>
                    <td class="p-2.5">
                      <template x-if="currentUser && currentUser.role === 'ADMIN'">
                        <input type="text" x-model="item.task" class="w-full p-1.5 text-sm border rounded-lg bg-white" placeholder="Rincian tugas...">
                      </template>
                      <template x-if="currentUser && currentUser.role === 'SUPERVISOR'">
                        <span class="font-medium text-slate-800 block py-1" x-text="item.task"></span>
                      </template>
                    </td>
                    <td class="p-2.5 text-center">
                      <template x-if="currentUser && currentUser.role === 'ADMIN'">
                        <input type="text" x-model="item.freq" class="w-full p-1.5 text-center text-sm border rounded-lg bg-white">
                      </template>
                      <template x-if="currentUser && currentUser.role === 'SUPERVISOR'">
                        <span class="text-xs text-slate-600" x-text="item.freq"></span>
                      </template>
                    </td>
                    <td class="p-2.5 text-center">
                      <template x-if="currentUser && currentUser.role === 'ADMIN'">
                        <input type="number" step="0.01" min="0" max="1" x-model.number="item.weight" class="w-20 p-1.5 text-center text-sm font-bold border rounded-lg bg-white">
                      </template>
                      <template x-if="currentUser && currentUser.role === 'SUPERVISOR'">
                        <span class="text-xs font-bold text-slate-700" x-text="Math.round(item.weight * 100) + '%'"></span>
                      </template>
                    </td>
                    <td class="p-2.5 text-center bg-blue-50/40">
                      <input type="number" min="0" max="100" x-model.number="item.score" class="w-20 p-1.5 text-center text-sm font-extrabold text-blue-900 border-2 border-blue-300 focus:border-blue-600 rounded-lg bg-white">
                    </td>
                    <td class="p-2.5 text-right font-bold text-emerald-700 text-xs" x-text="formatNum(item.weight * item.score)"></td>
                    <td x-show="currentUser && currentUser.role === 'ADMIN'" class="p-2.5 text-center">
                      <button @click="removeItem(idx)" class="p-1 text-rose-600 hover:bg-rose-50 rounded"><i data-lucide="trash-2" class="w-4 h-4"></i></button>
                    </td>
                  </tr>
                </template>
              </tbody>
            </table>
          </div>
 
          <div class="flex justify-end gap-2 pt-2">
            <button @click="jobdescModal.open = false" class="px-4 py-2 text-sm font-semibold bg-slate-100 rounded-xl">Tutup</button>
            <button @click="saveToStorage(); jobdescModal.open = false; showToast('Nilai kinerja berhasil disimpan!', 'success')" class="px-5 py-2 text-sm font-semibold text-white bg-emerald-600 hover:bg-emerald-700 rounded-xl shadow">Simpan Penilaian</button>
          </div>
        </div>
      </div>
    </div>
 
    <!-- =================================================================== -->
    <!-- MODAL TAMBAH / EDIT AKUN KEPALA BAGIAN (KHUSUS ADMIN)               -->
    <!-- =================================================================== -->
    <div x-show="supModal.open" style="display: none;" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-900/60 backdrop-blur-sm">
      <div @click.away="supModal.open = false" class="bg-white w-full max-w-md rounded-2xl shadow-2xl border overflow-hidden">
        <div class="px-6 py-4 bg-blue-900 text-white flex items-center justify-between">
          <h3 class="text-base font-bold" x-text="supModal.isEdit ? 'Edit Akun Kepala Bagian' : 'Tambah Akun Kepala Bagian'"></h3>
          <button @click="supModal.open = false" class="text-blue-200 hover:text-white"><i data-lucide="x" class="w-5 h-5"></i></button>
        </div>
        <form @submit.prevent="saveSupervisorForm()" class="p-6 space-y-4">
          <div>
            <label class="block text-xs font-bold text-slate-600 mb-1">Nama Kepala Bagian *</label>
            <input type="text" required x-model="supForm.name" placeholder="Contoh: Ns. Ahmad Fauzi" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
          </div>
          <div>
            <label class="block text-xs font-bold text-slate-600 mb-1">Bagian / Departemen *</label>
            <input type="text" required x-model="supForm.department" placeholder="Contoh: Keperawatan / Laboratorium" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
          </div>
          <div class="grid grid-cols-2 gap-3">
            <div>
              <label class="block text-xs font-bold text-slate-600 mb-1">Username Login *</label>
              <input type="text" required x-model="supForm.username" placeholder="Contoh: kabag_lab" class="w-full p-2.5 text-sm font-mono bg-slate-50 border rounded-xl">
            </div>
            <div>
              <label class="block text-xs font-bold text-slate-600 mb-1">Password / PIN *</label>
              <input type="text" required x-model="supForm.password" placeholder="Contoh: 123456" class="w-full p-2.5 text-sm font-mono bg-slate-50 border rounded-xl">
            </div>
          </div>
          <div class="flex justify-end gap-2 pt-2">
            <button type="button" @click="supModal.open = false" class="px-4 py-2 text-sm font-semibold bg-slate-100 rounded-xl">Batal</button>
            <button type="submit" class="px-5 py-2 text-sm font-semibold text-white bg-blue-600 rounded-xl shadow">Simpan Akun</button>
          </div>
        </form>
      </div>
    </div>
 
    <!-- =================================================================== -->
    <!-- MODAL ASSIGN / MAPPING KARYAWAN KE KEPALA BAGIAN                    -->
    <!-- =================================================================== -->
    <div x-show="assignModal.open" style="display: none;" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-900/60 backdrop-blur-sm overflow-y-auto">
      <div @click.away="assignModal.open = false" class="bg-white w-full max-w-2xl rounded-2xl shadow-2xl border overflow-hidden my-8">
        <div class="px-6 py-4 bg-slate-900 text-white flex items-center justify-between">
          <div>
            <h3 class="text-base font-bold" x-text="'Pilih Karyawan untuk Dinilai oleh: ' + (assignModal.sup ? assignModal.sup.name : '')"></h3>
            <p class="text-xs text-slate-300" x-text="assignModal.sup ? 'Bagian: ' + assignModal.sup.department : ''"></p>
          </div>
          <button @click="assignModal.open = false" class="text-slate-400 hover:text-white"><i data-lucide="x" class="w-5 h-5"></i></button>
        </div>
 
        <div class="p-6 space-y-4">
          <!-- Filter cepat di dalam modal assign -->
          <div class="flex flex-col sm:flex-row gap-2">
            <input type="text" x-model="assignSearch" placeholder="Cari nama atau jabatan karyawan..." class="flex-grow p-2 text-xs bg-slate-50 border rounded-xl">
            <select x-model="assignDeptFilter" class="p-2 text-xs bg-slate-50 border rounded-xl">
              <option value="ALL">Semua Organization</option>
              <template x-for="d in uniqueDepartments" :key="d">
                <option :value="d" x-text="d"></option>
              </template>
            </select>
            <button type="button" @click="selectAllFilteredForAssign()" class="px-3 py-2 bg-blue-50 hover:bg-blue-100 text-blue-700 text-xs font-bold rounded-xl whitespace-nowrap">Pilih Semua Tampil</button>
          </div>
 
          <div class="max-h-80 overflow-y-auto border rounded-xl divide-y divide-slate-100">
            <template x-for="emp in filteredEmployeesForAssign" :key="emp.id">
              <label class="flex items-center justify-between p-3 hover:bg-slate-50 cursor-pointer">
                <div class="flex items-center gap-3">
                  <input type="checkbox" :value="emp.id" x-model="assignSelectedIds" class="w-4 h-4 text-emerald-600 rounded border-slate-300 focus:ring-emerald-500">
                  <div>
                    <div class="text-sm font-bold text-slate-800" x-text="emp.name"></div>
                    <div class="text-xs text-slate-500" x-text="emp.nik + ' • ' + emp.department + ' (' + (emp.position || 'Staff') + ')'"></div>
                  </div>
                </div>
                <span class="px-2 py-0.5 text-[10px] font-bold rounded" :class="emp.unit === 'PT' ? 'bg-blue-100 text-blue-800' : 'bg-rose-100 text-rose-800'" x-text="emp.unit"></span>
              </label>
            </template>
          </div>
 
          <div class="flex items-center justify-between pt-2">
            <span class="text-xs font-bold text-emerald-700" x-text="assignSelectedIds.length + ' karyawan dipilih'"></span>
            <div class="flex gap-2">
              <button type="button" @click="assignModal.open = false" class="px-4 py-2 text-sm font-semibold bg-slate-100 rounded-xl">Batal</button>
              <button type="button" @click="saveAssignModal()" class="px-5 py-2 text-sm font-semibold text-white bg-emerald-600 hover:bg-emerald-700 rounded-xl shadow">Simpan Penugasan</button>
            </div>
          </div>
        </div>
      </div>
    </div>
 
    <!-- MODAL TAMBAH / EDIT KARYAWAN -->
    <div x-show="modal.open" style="display: none;" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-900/60 backdrop-blur-sm overflow-y-auto">
      <div @click.away="modal.open = false" class="bg-white w-full max-w-lg rounded-2xl shadow-2xl border overflow-hidden my-8">
        <div class="px-6 py-4 bg-slate-900 text-white flex items-center justify-between">
          <h3 class="text-base font-bold" x-text="modal.isEdit ? 'Edit Karyawan' : 'Tambah Karyawan Baru'"></h3>
          <button @click="modal.open = false" class="text-slate-400 hover:text-white"><i data-lucide="x" class="w-5 h-5"></i></button>
        </div>
        <form @submit.prevent="saveEmployeeForm()" class="p-6 space-y-4">
          <div>
            <label class="block text-xs font-bold text-slate-600 mb-1">Nama Lengkap *</label>
            <input type="text" required x-model="form.name" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
          </div>
          <div class="grid grid-cols-2 gap-2">
            <div>
              <label class="block text-xs font-bold text-slate-600 mb-1">NIK *</label>
              <input type="text" required x-model="form.nik" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
            </div>
            <div>
              <label class="block text-xs font-bold text-slate-600 mb-1">Unit Perusahaan *</label>
              <select x-model="form.unit" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
                <option value="PT">PT (MKK)</option>
                <option value="CV">CV (MGM)</option>
              </select>
            </div>
          </div>
          <div>
            <label class="block text-xs font-bold text-slate-600 mb-1">Organization / Departemen *</label>
            <input type="text" required x-model="form.department" placeholder="Contoh: Keperawatan / HRD" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
          </div>
          <div>
            <label class="block text-xs font-bold text-slate-600 mb-1">Jabatan</label>
            <input type="text" x-model="form.position" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
          </div>
          <div>
            <label class="block text-xs font-bold text-slate-600 mb-1">Gaji Pokok (Rp)</label>
            <input type="number" min="0" step="50000" x-model.number="form.baseSalary" class="w-full p-2.5 text-sm bg-slate-50 border rounded-xl">
          </div>
          <div class="flex justify-end gap-2 pt-2">
            <button type="button" @click="modal.open = false" class="px-4 py-2 text-sm font-semibold bg-slate-100 rounded-xl">Batal</button>
            <button type="submit" class="px-5 py-2 text-sm font-semibold text-white bg-emerald-600 rounded-xl shadow">Simpan</button>
          </div>
        </form>
      </div>
    </div>
 
    <!-- MODAL KONFIRMASI -->
    <div x-show="confirmModal.open" style="display: none;" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-900/60 backdrop-blur-sm">
      <div @click.away="confirmModal.open = false" class="bg-white w-full max-w-md rounded-2xl shadow-2xl border p-6 space-y-4">
        <div class="flex items-start gap-3">
          <div class="w-10 h-10 rounded-xl bg-rose-100 text-rose-600 flex items-center justify-center shrink-0"><i data-lucide="alert-triangle" class="w-5 h-5"></i></div>
          <div>
            <h3 class="text-base font-bold text-slate-900" x-text="confirmModal.title"></h3>
            <p class="text-xs text-slate-600 mt-1" x-text="confirmModal.message"></p>
          </div>
        </div>
        <div class="flex justify-end gap-2 pt-2">
          <button @click="confirmModal.open = false" class="px-4 py-2 text-xs font-semibold bg-slate-100 rounded-xl">Batal</button>
          <button @click="executeConfirmAction()" class="px-4 py-2 text-xs font-semibold text-white bg-rose-600 rounded-xl shadow">Ya, Lanjutkan</button>
        </div>
      </div>
    </div>
 
    <footer class="bg-white border-t border-slate-200 py-4 mt-8 no-print">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-xs text-slate-500">
        &copy; <span x-text="settings.year"></span> Sistem Penilaian Kinerja & Kompensasi — PT Medika Kesehatan Kerja & CV Medika Group Mandiri (v11 Tiered Late & Alpha Rules)
      </div>
    </footer>
  </div>
 
  <script>
    function appraisalApp() {
      return {
        currentUser: null,
        loginForm: { username: '', password: '' },
        loginError: '',
 
        activeTab: 'dashboard',
        toast: { show: false, message: '', type: 'success' },
        globalFilter: { search: '', unit: 'ALL', dept: 'ALL', status: 'ALL' },
        modal: { open: false, isEdit: false },
        jobdescModal: { open: false, emp: null },
        confirmModal: { open: false, title: '', message: '', actionType: '', targetId: null },
        form: { id: null, name: '', nik: '', unit: 'PT', department: '', position: '', baseSalary: 4500000 },
        categoryOptions: ['Sangat Baik (A)', 'Baik (B)', 'Cukup (C)', 'Kurang (D)'],
        copySourceEmpId: '',
 
        // Manajemen Kepala Bagian
        supervisors: [],
        supModal: { open: false, isEdit: false },
        supForm: { id: null, name: '', department: '', username: '', password: '', assignedEmpIds: [] },
        assignModal: { open: false, sup: null },
        assignSelectedIds: [],
        assignSearch: '',
        assignDeptFilter: 'ALL',
        
        settings: {
          year: 2025,
          adminPassword: 'admin123',
          weights: { absenMax: 30, kinerjaMax: 50, tahsinMax: 20 },
          absenPenaltyLate: 1,
          absenPenaltyAlpha: 5,
          lateRules: [
            { minDays: 0, maxDays: 0, penalty: 0 },
            { minDays: 1, maxDays: 4, penalty: 1 },
            { minDays: 5, maxDays: 10, penalty: 3 },
            { minDays: 11, maxDays: null, penalty: 7 }
          ],
          spDeductions: { NONE: 0, SP1: -10, SP2: -20, SP3: -30 },
          scoreRules: [
            { minScore: 90, maxScore: 120, category: 'Sangat Baik (A)', raisePercent: 10 },
            { minScore: 75, maxScore: 89.9, category: 'Baik (B)', raisePercent: 7 },
            { minScore: 60, maxScore: 74.9, category: 'Cukup (C)', raisePercent: 3 },
            { minScore: 0, maxScore: 59.9, category: 'Kurang (D)', raisePercent: 0 }
          ]
        },
        employees: [],
 
        defaultJobdes() {
          return [
            { task: 'Melaksanakan pelayanan sesuai standar operasional prosedur', freq: 'Setiap Hari', weight: 0.5, score: 85 },
            { task: 'Ketepatan pelaporan administrasi dan rekam medik', freq: '1 bulan 1x', weight: 0.3, score: 90 },
            { task: 'Koordinasi dan kerjasama dengan tim internal', freq: 'Setiap Hari', weight: 0.2, score: 85 }
          ];
        },
 
        defaultEmployees() {
          return [
            { id: 1, name: 'dr. Budi Santoso', nik: 'MKK-001', unit: 'PT', department: 'Pelayanan Medis', position: 'Dokter Umum', baseSalary: 8500000, absenLate: 1, absenAlpha: 0, spStatus: 'NONE', tahsinScore: 88, directorAdj: 3, directorNote: 'Penanggung jawab MCU', jobdesItems: [
              { task: 'Pemeriksaan pasien umum & MCU', freq: 'Setiap Hari', weight: 0.6, score: 95 },
              { task: 'Pencatatan rekam medis digital', freq: 'Setiap Hari', weight: 0.4, score: 90 }
            ]},
            { id: 2, name: 'Siti Rahmawati, Amd.Kep', nik: 'MGM-004', unit: 'CV', department: 'Keperawatan', position: 'Perawat Pelaksana', baseSalary: 4800000, absenLate: 2, absenAlpha: 0, spStatus: 'NONE', tahsinScore: 85, directorAdj: 0, directorNote: '', jobdesItems: [
              { task: 'Tindakan keperawatan & triage pasien', freq: 'Setiap Hari', weight: 0.5, score: 88 },
              { task: 'Sterilisasi alat medis klinik', freq: 'Setiap Hari', weight: 0.3, score: 85 },
              { task: 'Laporan shift harian', freq: 'Setiap Hari', weight: 0.2, score: 85 }
            ]},
            { id: 3, name: 'Rizky Pratama, S.E.', nik: 'MKK-009', unit: 'PT', department: 'Keuangan & Admin', position: 'Staff Keuangan', baseSalary: 5200000, absenLate: 4, absenAlpha: 0, spStatus: 'NONE', tahsinScore: 78, directorAdj: 2, directorNote: 'Ketepatan laporan pajak', jobdesItems: [
              { task: 'Pencatatan kas masuk & keluar', freq: 'Setiap Hari', weight: 0.4, score: 80 },
              { task: 'Pembuatan invoice & rekap tagihan vendor', freq: '1 bulan 1x', weight: 0.4, score: 82 },
              { task: 'Arsip dokumen pajak', freq: '1 bulan 1x', weight: 0.2, score: 75 }
            ]}
          ];
        },
 
        defaultSupervisors() {
          return [
            { id: 101, name: 'Kepala Bagian Pelayanan & Keperawatan', department: 'Keperawatan & Medis', username: 'kabag_medis', password: '123', assignedEmpIds: [1, 2] },
            { id: 102, name: 'Kepala Bagian Keuangan & Admin', department: 'Keuangan & Admin', username: 'kabag_keu', password: '123', assignedEmpIds: [3] }
          ];
        },
 
        initApp() {
          const defaultLateRules = [
            { minDays: 0, maxDays: 0, penalty: 0 },
            { minDays: 1, maxDays: 4, penalty: 1 },
            { minDays: 5, maxDays: 10, penalty: 3 },
            { minDays: 11, maxDays: null, penalty: 7 }
          ];

          const s = localStorage.getItem('appraisal_settings_v6') || localStorage.getItem('appraisal_settings_v5');
          const e = localStorage.getItem('appraisal_employees_v6') || localStorage.getItem('appraisal_employees_v5');
          const sup = localStorage.getItem('appraisal_supervisors_v7');
 
          if (s) { 
            try { 
              const parsedS = JSON.parse(s);
              this.settings = { ...this.settings, ...parsedS };
              if (!this.settings.adminPassword) this.settings.adminPassword = 'admin123';
              if (!Array.isArray(this.settings.lateRules) || this.settings.lateRules.length === 0) {
                this.settings.lateRules = JSON.parse(JSON.stringify(defaultLateRules));
              }
              if (this.settings.absenPenaltyAlpha === undefined || this.settings.absenPenaltyAlpha === null) {
                this.settings.absenPenaltyAlpha = 5;
              }
            } catch(err){} 
          }
          if (e) { 
            try { this.employees = JSON.parse(e); } catch(err){ this.employees = this.defaultEmployees(); } 
          } else { 
            this.employees = this.defaultEmployees(); 
          }
 
          if (sup) {
            try { this.supervisors = JSON.parse(sup); } catch(err){ this.supervisors = this.defaultSupervisors(); }
          } else {
            this.supervisors = this.defaultSupervisors();
          }
          this.cleanupDeletedAssignedEmployees();
 
          const savedSession = sessionStorage.getItem('appraisal_session_v7');
          if (savedSession) {
            try {
              this.currentUser = JSON.parse(savedSession);
              if (this.currentUser.role === 'SUPERVISOR') {
                this.activeTab = 'kinerja';
              }
            } catch(err){}
          }
 
          this.$nextTick(() => lucide.createIcons());
        },
 
        cleanupDeletedAssignedEmployees() {
          const validIds = new Set(this.employees.map(e => String(e.id)));
          if (Array.isArray(this.supervisors)) {
            this.supervisors.forEach(s => {
              if (Array.isArray(s.assignedEmpIds)) {
                s.assignedEmpIds = s.assignedEmpIds.filter(id => validIds.has(String(id)));
              }
            });
          }
        },
 
        saveToStorage() {
          this.cleanupDeletedAssignedEmployees();
          localStorage.setItem('appraisal_settings_v6', JSON.stringify(this.settings));
          localStorage.setItem('appraisal_employees_v6', JSON.stringify(this.employees));
          localStorage.setItem('appraisal_supervisors_v7', JSON.stringify(this.supervisors));
          this.$nextTick(() => lucide.createIcons());
        },
 
        // ==========================================
        // LOGIN & LOGOUT HANDLERS
        // ==========================================
        quickFillLogin(u, p) {
          this.loginForm.username = u;
          this.loginForm.password = p;
          this.loginError = '';
        },
 
        handleLogin() {
          this.loginError = '';
          const u = this.loginForm.username.trim();
          const p = this.loginForm.password.trim();
 
          if (u === 'admin' && p === (this.settings.adminPassword || 'admin123')) {
            this.currentUser = { role: 'ADMIN', name: 'Admin / HRD', department: 'Manajemen Pusat' };
            sessionStorage.setItem('appraisal_session_v7', JSON.stringify(this.currentUser));
            this.activeTab = 'dashboard';
            this.showToast('Selamat datang, Admin / HRD!', 'success');
            this.$nextTick(() => lucide.createIcons());
            return;
          }
 
          const foundSup = this.supervisors.find(s => s.username === u && s.password === p);
          if (foundSup) {
            this.currentUser = {
              role: 'SUPERVISOR',
              id: foundSup.id,
              name: foundSup.name,
              department: foundSup.department
            };
            sessionStorage.setItem('appraisal_session_v7', JSON.stringify(this.currentUser));
            this.activeTab = 'kinerja';
            this.globalFilter = { search: '', unit: 'ALL', dept: 'ALL', status: 'ALL' };
            this.showToast(`Selamat datang, ${foundSup.name}!`, 'success');
            this.$nextTick(() => lucide.createIcons());
            return;
          }
 
          this.loginError = 'Username atau Password salah. Silakan periksa kembali.';
        },
 
        handleLogout() {
          this.currentUser = null;
          sessionStorage.removeItem('appraisal_session_v7');
          this.loginForm = { username: '', password: '' };
          this.loginError = '';
          this.$nextTick(() => lucide.createIcons());
        },
 
        // ==========================================
        // MANAJEMEN AKUN KEPALA BAGIAN & MAPPING
        // ==========================================
        openAddSupervisorModal() {
          this.supModal.isEdit = false;
          this.supForm = { id: Date.now(), name: '', department: '', username: '', password: '123', assignedEmpIds: [] };
          this.supModal.open = true;
          this.$nextTick(() => lucide.createIcons());
        },
        openEditSupervisorModal(sup) {
          this.supModal.isEdit = true;
          this.supForm = JSON.parse(JSON.stringify(sup));
          this.supModal.open = true;
          this.$nextTick(() => lucide.createIcons());
        },
        saveSupervisorForm() {
          if (this.supForm.username.trim().toLowerCase() === 'admin') {
            this.showToast('Username "admin" sudah digunakan sistem.', 'warning');
            return;
          }
          if (this.supModal.isEdit) {
            const idx = this.supervisors.findIndex(s => s.id === this.supForm.id);
            if (idx !== -1) this.supervisors[idx] = { ...this.supForm };
            this.showToast('Akun Kepala Bagian diperbarui!', 'success');
          } else {
            this.supervisors.push({ ...this.supForm });
            this.showToast('Akun Kepala Bagian berhasil dibuat!', 'success');
          }
          this.supModal.open = false;
          this.saveToStorage();
        },
        deleteSupervisor(id) {
          this.supervisors = this.supervisors.filter(s => s.id !== id);
          this.saveToStorage();
          this.showToast('Akun Kepala Bagian dihapus.', 'info');
        },
 
        openAssignModal(sup) {
          this.assignModal = { open: true, sup };
          this.assignSelectedIds = [...(sup.assignedEmpIds || [])];
          this.assignSearch = '';
          this.assignDeptFilter = 'ALL';
          this.$nextTick(() => lucide.createIcons());
        },
        get filteredEmployeesForAssign() {
          return this.employees.filter(emp => {
            const mSearch = !this.assignSearch || emp.name.toLowerCase().includes(this.assignSearch.toLowerCase()) || (emp.position && emp.position.toLowerCase().includes(this.assignSearch.toLowerCase()));
            const mDept = this.assignDeptFilter === 'ALL' || emp.department === this.assignDeptFilter;
            return mSearch && mDept;
          });
        },
        selectAllFilteredForAssign() {
          const currentSet = new Set((this.assignSelectedIds || []).map(id => String(id)));
          this.filteredEmployeesForAssign.forEach(emp => {
            const sid = String(emp.id);
            if (!currentSet.has(sid)) {
              currentSet.add(sid);
              this.assignSelectedIds.push(sid);
            }
          });
        },
        saveAssignModal() {
          if (this.assignModal.sup) {
            const targetSup = this.supervisors.find(s => String(s.id) === String(this.assignModal.sup.id)) || this.assignModal.sup;
            targetSup.assignedEmpIds = (this.assignSelectedIds || []).map(id => String(id));
            this.saveToStorage();
            this.showToast(`Daftar karyawan untuk ${targetSup.name} disimpan!`, 'success');
          }
          this.assignModal.open = false;
        },
        getValidAssignedEmpIds(sup) {
          if (!sup || !Array.isArray(sup.assignedEmpIds)) return [];
          const validIds = new Set(this.employees.map(e => String(e.id)));
          return sup.assignedEmpIds.filter(id => validIds.has(String(id)));
        },
 
        getEmployeeNameById(id) {
          const emp = this.employees.find(e => String(e.id) === String(id));
          return emp ? `${emp.name} (${emp.department})` : '';
        },
 
        // ==========================================
        // FILTER KARYAWAN BERDASARKAN ROLE LOGIN
        // ==========================================
        get roleFilteredEmployees() {
          let baseList = this.filteredEmployees;
          if (this.currentUser && this.currentUser.role === 'SUPERVISOR') {
            const sup = this.supervisors.find(s => String(s.id) === String(this.currentUser.id));
            const allowedSet = new Set((sup && Array.isArray(sup.assignedEmpIds) ? sup.assignedEmpIds : []).map(id => String(id)));
            baseList = baseList.filter(emp => allowedSet.has(String(emp.id)));
          }
          return baseList;
        },
 
        // ==========================================
        // BACKUP & RESTORE JSON (TERMASUK AKUN KABAG)
        // ==========================================
        exportDataJSON() {
          const backupData = {
            app: "Appraisal_PT_MKK_CV_MGM",
            version: "v11",
            exportDate: new Date().toISOString(),
            settings: this.settings,
            employees: this.employees,
            supervisors: this.supervisors
          };
          const jsonStr = JSON.stringify(backupData, null, 2);
          const blob = new Blob([jsonStr], { type: 'application/json' });
          const url = URL.createObjectURL(blob);
          const a = document.createElement('a');
          a.href = url;
          const dateStr = new Date().toISOString().slice(0, 10);
          a.download = `Backup_Penilaian_Kinerja_${this.settings.year}_${dateStr}.json`;
          document.body.appendChild(a);
          a.click();
          document.body.removeChild(a);
          URL.revokeObjectURL(url);
          this.showToast('File Backup JSON berhasil diunduh!', 'success');
        },
 
        importDataJSON(event) {
          const file = event.target.files[0];
          if (!file) return;
          const reader = new FileReader();
          reader.onload = (e) => {
            try {
              const parsed = JSON.parse(e.target.result);
              let restoredSettings = parsed.settings;
              let restoredEmployees = parsed.employees;
              let restoredSupervisors = parsed.supervisors;
 
              if (typeof restoredSettings === 'string') restoredSettings = JSON.parse(restoredSettings);
              if (typeof restoredEmployees === 'string') restoredEmployees = JSON.parse(restoredEmployees);
              if (typeof restoredSupervisors === 'string') restoredSupervisors = JSON.parse(restoredSupervisors);
 
              if (restoredSettings && Array.isArray(restoredEmployees)) {
                this.settings = { ...this.settings, ...restoredSettings };
                if (!Array.isArray(this.settings.lateRules) || this.settings.lateRules.length === 0) {
                  this.settings.lateRules = [
                    { minDays: 0, maxDays: 0, penalty: 0 },
                    { minDays: 1, maxDays: 4, penalty: 1 },
                    { minDays: 5, maxDays: 10, penalty: 3 },
                    { minDays: 11, maxDays: null, penalty: 7 }
                  ];
                }
                this.employees = restoredEmployees;
                if (Array.isArray(restoredSupervisors)) {
                  this.supervisors = restoredSupervisors;
                }
                this.saveToStorage();
                this.showToast(`Berhasil memulihkan ${this.employees.length} data karyawan dari file JSON!`, 'success');
              } else {
                this.showToast('Format file JSON tidak valid atau rusak.', 'warning');
              }
            } catch (err) {
              console.error(err);
              this.showToast('Gagal membaca file JSON.', 'warning');
            }
          };
          reader.readAsText(file);
          event.target.value = '';
        },
 
        resetDefaultSettings() {
          this.settings = {
            year: 2025,
            adminPassword: 'admin123',
            weights: { absenMax: 30, kinerjaMax: 50, tahsinMax: 20 },
            absenPenaltyLate: 1,
            absenPenaltyAlpha: 5,
            lateRules: [
              { minDays: 0, maxDays: 0, penalty: 0 },
              { minDays: 1, maxDays: 4, penalty: 1 },
              { minDays: 5, maxDays: 10, penalty: 3 },
              { minDays: 11, maxDays: null, penalty: 7 }
            ],
            spDeductions: { NONE: 0, SP1: -10, SP2: -20, SP3: -30 },
            scoreRules: [
              { minScore: 90, maxScore: 120, category: 'Sangat Baik (A)', raisePercent: 10 },
              { minScore: 75, maxScore: 89.9, category: 'Baik (B)', raisePercent: 7 },
              { minScore: 60, maxScore: 74.9, category: 'Cukup (C)', raisePercent: 3 },
              { minScore: 0, maxScore: 59.9, category: 'Kurang (D)', raisePercent: 0 }
            ]
          };
          this.saveToStorage();
          this.showToast('Pengaturan dikembalikan ke default.', 'info');
        },
 
        addScoreRule() {
          this.settings.scoreRules.push({ minScore: 0, maxScore: 50, category: 'Baik (B)', raisePercent: 0 });
          this.saveToStorage();
        },
        removeScoreRule(idx) {
          if (this.settings.scoreRules.length <= 1) return;
          this.settings.scoreRules.splice(idx, 1);
          this.saveToStorage();
        },
 
        openJobdescModal(emp) {
          if (!emp) return;
          if (!emp.jobdesItems || emp.jobdesItems.length === 0) {
            emp.jobdesItems = JSON.parse(JSON.stringify(this.defaultJobdes()));
          }
          this.copySourceEmpId = '';
          this.jobdescModal = { open: true, emp };
          this.$nextTick(() => lucide.createIcons());
        },
 
        copyJobdescFromOther() {
          if (!this.copySourceEmpId || !this.jobdescModal.emp) {
            this.showToast('Pilih karyawan sumber terlebih dahulu.', 'warning');
            return;
          }
          const sourceEmp = this.employees.find(e => e.id == this.copySourceEmpId);
          if (sourceEmp && sourceEmp.jobdesItems && sourceEmp.jobdesItems.length > 0) {
            this.jobdescModal.emp.jobdesItems = JSON.parse(JSON.stringify(sourceEmp.jobdesItems));
            this.showToast(`Jobdesc berhasil disalin dari ${sourceEmp.name}!`, 'success');
          } else {
            this.showToast('Karyawan sumber tidak memiliki item jobdesc.', 'warning');
          }
        },
 
        getTotalJobdesWeight(emp) {
          if (!emp || !emp.jobdesItems) return 0;
          const sum = emp.jobdesItems.reduce((acc, item) => acc + (Number(item.weight) || 0), 0);
          return Math.round(sum * 100) / 100;
        },

        // ==========================================
        // PERHITUNGAN ABSEN (TIER TERLAMBAT & ALPHA)
        // ==========================================
        getLateRules() {
          const defaultRules = [
            { minDays: 0, maxDays: 0, penalty: 0 },
            { minDays: 1, maxDays: 4, penalty: 1 },
            { minDays: 5, maxDays: 10, penalty: 3 },
            { minDays: 11, maxDays: null, penalty: 7 }
          ];
          if (Array.isArray(this.settings.lateRules) && this.settings.lateRules.length > 0) {
            return this.settings.lateRules;
          }
          return defaultRules;
        },

        getLateRulesSummary() {
          const rules = this.getLateRules();
          return rules.map(r => {
            const minD = Number(r.minDays) || 0;
            const hasMax = r.maxDays !== null && r.maxDays !== undefined && r.maxDays !== '';
            const rangeText = !hasMax ? `${minD}+ hr` : (minD === Number(r.maxDays) ? `${minD} hr` : `${minD}-${Number(r.maxDays)} hr`);
            return `${rangeText} = -${Number(r.penalty) || 0} pt`;
          }).join(', ');
        },

        calcLatePenalty(lateDays) {
          const days = Math.max(0, Number(lateDays) || 0);
          const rules = this.getLateRules();

          const matched = rules.find(r => {
            const minD = Number(r.minDays) || 0;
            const hasMax = r.maxDays !== null && r.maxDays !== undefined && r.maxDays !== '';
            const maxD = hasMax ? Number(r.maxDays) : Infinity;
            return days >= minD && days <= maxD;
          });

          if (matched) {
            return Math.max(0, Number(matched.penalty) || 0);
          }

          const sortedDesc = [...rules].sort((a, b) => (Number(b.minDays) || 0) - (Number(a.minDays) || 0));
          return sortedDesc.length > 0 ? Math.max(0, Number(sortedDesc[0].penalty) || 0) : 0;
        },

        calcAlphaPenalty(alphaDays) {
          const days = Math.max(0, Number(alphaDays) || 0);
          const rate = Math.max(0, Number(this.settings.absenPenaltyAlpha) || 0);
          return days * rate;
        },
 
        calcAbsenPoints(emp) {
          const max = Number(this.settings.weights.absenMax) || 0;
          const latePenalty = this.calcLatePenalty(emp.absenLate);
          const alphaPenalty = this.calcAlphaPenalty(emp.absenAlpha);
          return Math.max(0, max - latePenalty - alphaPenalty);
        },
 
        calcKinerjaPoints(emp) {
          if (!emp || !emp.jobdesItems || emp.jobdesItems.length === 0) return 0;
          let weightedSum = 0;
          let totalWeight = 0;
          emp.jobdesItems.forEach(item => {
            const w = Number(item.weight) || 0;
            const s = Number(item.score) || 0;
            weightedSum += w * s;
            totalWeight += w;
          });
          const finalScore100 = totalWeight > 0 ? (weightedSum / totalWeight) : 0;
          const maxKinerja = Number(this.settings.weights.kinerjaMax) || 50;
          return (finalScore100 / 100) * maxKinerja;
        },
 
        calcSpPoints(emp) { return Number(this.settings.spDeductions[emp.spStatus]) || 0; },
        calcTahsinPoints(emp) {
          const score = Math.min(100, Math.max(0, Number(emp.tahsinScore) || 0));
          return (score / 100) * (Number(this.settings.weights.tahsinMax) || 20);
        },
        calcTotalScore(emp) {
          return Math.max(0, this.calcAbsenPoints(emp) + this.calcKinerjaPoints(emp) + this.calcSpPoints(emp) + this.calcTahsinPoints(emp) + (Number(emp.directorAdj) || 0));
        },
 
        getMatchedRule(emp) {
          const total = Number(this.calcTotalScore(emp));
          const exact = this.settings.scoreRules.find(r => total >= Number(r.minScore) && total <= Number(r.maxScore));
          if (exact) return exact;
          const sorted = [...this.settings.scoreRules].sort((a, b) => Number(b.maxScore) - Number(a.maxScore));
          if (sorted.length > 0 && total > Number(sorted[0].maxScore)) return sorted[0];
          return sorted[sorted.length - 1] || { category: 'Belum Diatur', raisePercent: 0 };
        },
 
        getGradeLabel(emp) { return this.getMatchedRule(emp).category; },
        getMatchedRuleRangeText(emp) {
          const rule = this.getMatchedRule(emp);
          return rule ? `Range: ${rule.minScore} - ${rule.maxScore}` : '';
        },
        getSalaryIncreaseRate(emp) { return Number(this.getMatchedRule(emp).raisePercent) || 0; },
        calcNewSalary(emp) {
          const base = Number(emp.baseSalary) || 0;
          return base + (base * (this.getSalaryIncreaseRate(emp) / 100));
        },
        isGoodCategory(emp) {
          const c = (this.getGradeLabel(emp) || '').toLowerCase();
          return !c.includes('kurang') && !c.includes('cukup');
        },
 
        get uniqueDepartments() { return [...new Set(this.employees.map(e => e.department).filter(Boolean))].sort(); },
        get uniqueRuleCategories() { return [...new Set(this.settings.scoreRules.map(r => r.category))]; },
        
        get filteredEmployees() {
          return this.employees.filter(emp => {
            const matchSearch = !this.globalFilter.search || emp.name.toLowerCase().includes(this.globalFilter.search.toLowerCase()) || emp.nik.toLowerCase().includes(this.globalFilter.search.toLowerCase()) || (emp.position && emp.position.toLowerCase().includes(this.globalFilter.search.toLowerCase()));
            const matchUnit = this.globalFilter.unit === 'ALL' || emp.unit === this.globalFilter.unit;
            const matchDept = this.globalFilter.dept === 'ALL' || emp.department === this.globalFilter.dept;
            const matchStatus = this.globalFilter.status === 'ALL' || this.getGradeLabel(emp) === this.globalFilter.status;
            return matchSearch && matchUnit && matchDept && matchStatus;
          });
        },
        get filteredMasterEmployees() {
          return this.employees.filter(emp => {
            const matchSearch = !this.globalFilter.search || emp.name.toLowerCase().includes(this.globalFilter.search.toLowerCase()) || emp.nik.toLowerCase().includes(this.globalFilter.search.toLowerCase());
            const matchUnit = this.globalFilter.unit === 'ALL' || emp.unit === this.globalFilter.unit;
            return matchSearch && matchUnit;
          });
        },
 
        countByUnit(u) { return this.employees.filter(e => e.unit === u).length; },
        get goodCategoryCount() { return this.filteredEmployees.filter(e => this.isGoodCategory(e)).length; },
        get notGoodCategoryCount() { return this.filteredEmployees.filter(e => !this.isGoodCategory(e)).length; },
        get averageTotalScore() {
          if (!this.filteredEmployees.length) return 0;
          return (this.filteredEmployees.reduce((a, e) => a + this.calcTotalScore(e), 0) / this.filteredEmployees.length).toFixed(1);
        },
        get averageSalaryIncrease() {
          if (!this.filteredEmployees.length) return 0;
          return (this.filteredEmployees.reduce((a, e) => a + this.getSalaryIncreaseRate(e), 0) / this.filteredEmployees.length).toFixed(1);
        },
 
        switchTab(tab) { this.activeTab = tab; this.$nextTick(() => lucide.createIcons()); },
        showToast(msg, type = 'success') {
          this.toast = { show: true, message: msg, type };
          setTimeout(() => { this.toast.show = false; }, 3500);
        },
 
        openAddEmployeeModal() {
          this.modal.isEdit = false;
          this.form = { id: Date.now(), name: '', nik: '', unit: 'PT', department: '', position: '', baseSalary: 4500000, jobdesItems: JSON.parse(JSON.stringify(this.defaultJobdes())) };
          this.modal.open = true;
          this.$nextTick(() => lucide.createIcons());
        },
        openEditEmployeeModal(emp) {
          this.modal.isEdit = true;
          this.form = JSON.parse(JSON.stringify(emp));
          this.modal.open = true;
          this.$nextTick(() => lucide.createIcons());
        },
        saveEmployeeForm() {
          if (this.modal.isEdit) {
            const idx = this.employees.findIndex(e => e.id === this.form.id);
            if (idx !== -1) this.employees[idx] = { ...this.form };
            this.showToast('Data karyawan diperbarui!', 'success');
          } else {
            this.employees.push({ ...this.form, absenLate: 0, absenAlpha: 0, spStatus: 'NONE', tahsinScore: 80, directorAdj: 0, directorNote: '' });
            this.showToast('Karyawan ditambahkan!', 'success');
          }
          this.modal.open = false;
          this.saveToStorage();
        },
        confirmDeleteEmployee(emp) {
          this.confirmModal = { open: true, title: 'Hapus Karyawan?', message: `Hapus "${emp.name}"?`, actionType: 'delete_one', targetId: emp.id };
          this.$nextTick(() => lucide.createIcons());
        },
        openResetDummyModal() {
          this.confirmModal = { open: true, title: 'Kosongkan Data?', message: 'Semua data akan dihapus.', actionType: 'clear_all', targetId: null };
          this.$nextTick(() => lucide.createIcons());
        },
        executeConfirmAction() {
          if (this.confirmModal.actionType === 'delete_one') {
            this.employees = this.employees.filter(e => e.id !== this.confirmModal.targetId);
            this.showToast('Karyawan dihapus.', 'warning');
          } else if (this.confirmModal.actionType === 'clear_all') {
            this.employees = [];
            this.showToast('Data dikosongkan.', 'info');
          }
          this.confirmModal.open = false;
          this.saveToStorage();
        },
 
        downloadTemplate(type) {
          let rows = [['Nama Lengkap', 'NIK', 'Unit (PT/CV)', 'Organization', 'Jabatan', 'Gaji Pokok']];
          const ws = XLSX.utils.aoa_to_sheet(rows);
          const wb = XLSX.utils.book_new();
          XLSX.utils.book_append_sheet(wb, ws, 'Template');
          XLSX.writeFile(wb, 'Template_Master_Karyawan.xlsx');
          this.showToast('Template diunduh!', 'info');
        },
        handleFileUpload(e) {
          const file = e.target.files[0];
          if (!file) return;
          const reader = new FileReader();
          reader.onload = (evt) => {
            try {
              const data = new Uint8Array(evt.target.result);
              const workbook = XLSX.read(data, { type: 'array' });
              const firstSheetName = workbook.SheetNames[0];
              const worksheet = workbook.Sheets[firstSheetName];
              const json = XLSX.utils.sheet_to_json(worksheet, { defval: '' });
              
              if (json.length === 0) {
                this.showToast('File Excel kosong atau format tidak sesuai.', 'warning');
                return;
              }
 
              let addedCount = 0;
              json.forEach(row => {
                const name = row['Nama Lengkap'] || row['Nama'] || row['nama'] || '';
                const nik = String(row['NIK'] || row['nik'] || row['Employee ID'] || ('MKK-' + Math.floor(1000 + Math.random() * 9000)));
                let unit = String(row['Unit (PT/CV)'] || row['Unit'] || row['unit'] || 'PT').toUpperCase();
                if (unit.includes('CV') || unit.includes('MGM')) unit = 'CV'; else unit = 'PT';
                const department = row['Organization'] || row['Departemen'] || row['department'] || 'Umum';
                const position = row['Jabatan'] || row['position'] || '';
                const baseSalary = Number(row['Gaji Pokok'] || row['gaji'] || row['baseSalary'] || 4500000);
 
                if (name) {
                  const existing = this.employees.find(emp => emp.nik === nik);
                  if (existing) {
                    existing.name = name;
                    existing.unit = unit;
                    existing.department = department;
                    existing.position = position;
                    existing.baseSalary = baseSalary;
                  } else {
                    this.employees.push({
                      id: Date.now() + Math.random(),
                      name,
                      nik,
                      unit,
                      department,
                      position,
                      baseSalary,
                      absenLate: 0,
                      absenAlpha: 0,
                      spStatus: 'NONE',
                      tahsinScore: 80,
                      directorAdj: 0,
                      directorNote: '',
                      jobdesItems: JSON.parse(JSON.stringify(this.defaultJobdes()))
                    });
                  }
                  addedCount++;
                }
              });
 
              this.saveToStorage();
              this.showToast(`Berhasil mengimpor ${addedCount} data karyawan!`, 'success');
            } catch (err) {
              console.error(err);
              this.showToast('Gagal membaca file Excel. Pastikan format benar.', 'warning');
            }
          };
          reader.readAsArrayBuffer(file);
          e.target.value = '';
        },
 
        formatNum(v) { const n = Number(v) || 0; return Number.isInteger(n) ? n : n.toFixed(1); },
        formatRupiah(v) { return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR', maximumFractionDigits: 0 }).format(v); },
 
        exportExcel() {
          const rows = [['NIK', 'Nama Lengkap', 'Unit', 'Organization', 'Jabatan', 'Absen', 'Kinerja', 'SP', 'Tahsin', 'Lain-Lain', 'Total Skor', 'Kategori', 'Kenaikan (%)', 'Gaji Baru']];
          this.filteredEmployees.forEach(e => {
            rows.push([e.nik, e.name, e.unit, e.department, e.position || '-', this.calcAbsenPoints(e), this.calcKinerjaPoints(e), this.calcSpPoints(e), this.calcTahsinPoints(e), e.directorAdj, this.calcTotalScore(e), this.getGradeLabel(e), this.getSalaryIncreaseRate(e) + '%', Math.round(this.calcNewSalary(e))]);
          });
          const ws = XLSX.utils.aoa_to_sheet(rows);
          const wb = XLSX.utils.book_new();
          XLSX.utils.book_append_sheet(wb, ws, 'Rekap Penilaian');
          XLSX.writeFile(wb, `Rekap_Penilaian_${this.settings.year}.xlsx`);
          this.showToast('File Excel diexport!', 'success');
        },
        getCategoryBadgeClass(emp) {
          const c = (this.getGradeLabel(emp) || '').toLowerCase();
          if (c.includes('sangat baik')) return 'bg-emerald-100 text-emerald-800 border border-emerald-200';
          if (c.includes('baik')) return 'bg-blue-100 text-blue-800 border border-blue-200';
          if (c.includes('cukup')) return 'bg-amber-100 text-amber-800 border border-amber-200';
          return 'bg-rose-100 text-rose-800 border border-rose-200';
        },
        getCategoryDotClass(emp) {
          const c = (this.getGradeLabel(emp) || '').toLowerCase();
          if (c.includes('sangat baik')) return 'bg-emerald-600';
          if (c.includes('baik')) return 'bg-blue-600';
          if (c.includes('cukup')) return 'bg-amber-600';
          return 'bg-rose-600';
        },
        getRuleRowStyle(cat) { return 'bg-slate-50 border-slate-200'; }
      };
    }
  </script>
</body>
</html>
