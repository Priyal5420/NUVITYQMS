export default function NuvityQMSDashboard() {
  const dashboardCards = [
    {
      title: 'Open CAPA',
      value: '07',
      color: 'bg-red-500',
    },
    {
      title: 'Audit Due',
      value: '03',
      color: 'bg-yellow-500',
    },
    {
      title: 'Training Due',
      value: '12',
      color: 'bg-blue-500',
    },
    {
      title: 'Calibration Due',
      value: '05',
      color: 'bg-green-500',
    },
  ]

  const documents = [
    {
      code: 'NQMS-SOP-001',
      name: 'Incoming Inspection SOP',
      department: 'Quality',
      revision: 'R01',
      status: 'Approved',
    },
    {
      code: 'NQMS-FRM-002',
      name: 'CAPA Format',
      department: 'QA',
      revision: 'R00',
      status: 'Active',
    },
    {
      code: 'NQMS-WI-003',
      name: 'Machine Cleaning WI',
      department: 'Production',
      revision: 'R02',
      status: 'Approved',
    },
  ]

  const capaData = [
    {
      issue: 'Customer Complaint',
      rootCause: 'Improper Inspection',
      action: 'Inspection Training',
      status: 'Open',
    },
    {
      issue: 'Machine Breakdown',
      rootCause: 'No PM',
      action: 'PM Schedule Implemented',
      status: 'Closed',
    },
  ]

  return (
    <div className='min-h-screen bg-gray-100'>
      {/* Top Navbar */}
      <div className='bg-blue-950 text-white px-8 py-5 flex justify-between items-center shadow-lg'>
        <div>
          <h1 className='text-3xl font-bold'>NUVITYQMS</h1>
          <p className='text-sm text-gray-300'>ISO • Lean • MSME Management System</p>
        </div>

        <div className='flex gap-4 items-center'>
          <button className='bg-white text-blue-950 px-5 py-2 rounded-xl font-semibold'>
            Admin Panel
          </button>

          <div className='w-12 h-12 rounded-full bg-blue-400 flex items-center justify-center text-xl font-bold'>
            P
          </div>
        </div>
      </div>

      <div className='flex'>
        {/* Sidebar */}
        <div className='w-72 bg-white min-h-screen shadow-xl p-6'>
          <h2 className='text-xl font-bold mb-8 text-blue-950'>Main Menu</h2>

          <div className='space-y-4'>
            <button className='w-full text-left bg-blue-950 text-white px-5 py-3 rounded-2xl'>
              Dashboard
            </button>

            <button className='w-full text-left bg-gray-100 px-5 py-3 rounded-2xl hover:bg-blue-100'>
              Document Control
            </button>

            <button className='w-full text-left bg-gray-100 px-5 py-3 rounded-2xl hover:bg-blue-100'>
              Audit Management
            </button>

            <button className='w-full text-left bg-gray-100 px-5 py-3 rounded-2xl hover:bg-blue-100'>
              CAPA Tracker
            </button>

            <button className='w-full text-left bg-gray-100 px-5 py-3 rounded-2xl hover:bg-blue-100'>
              Training Records
            </button>

            <button className='w-full text-left bg-gray-100 px-5 py-3 rounded-2xl hover:bg-blue-100'>
              Calibration
            </button>

            <button className='w-full text-left bg-gray-100 px-5 py-3 rounded-2xl hover:bg-blue-100'>
              Notifications
            </button>
          </div>
        </div>

        {/* Main Dashboard */}
        <div className='flex-1 p-8'>
          {/* Welcome */}
          <div className='mb-8'>
            <h2 className='text-4xl font-bold text-gray-800'>Welcome to NUVITYQMS</h2>
            <p className='text-gray-500 mt-2'>Manage ISO systems, Lean tools, audits, and documentation from one platform.</p>
          </div>

          {/* Dashboard Cards */}
          <div className='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-10'>
            {dashboardCards.map((card, index) => (
              <div
                key={index}
                className={`${card.color} text-white rounded-3xl p-6 shadow-xl hover:scale-105 transition`}
              >
                <h3 className='text-lg font-medium'>{card.title}</h3>
                <p className='text-5xl font-bold mt-4'>{card.value}</p>
              </div>
            ))}
          </div>

          {/* Document Control Table */}
          <div className='bg-white rounded-3xl shadow-xl p-6 mb-10'>
            <div className='flex justify-between items-center mb-6'>
              <h2 className='text-2xl font-bold text-blue-950'>Document Control</h2>

              <button className='bg-blue-950 text-white px-5 py-2 rounded-xl'>
                Add Document
              </button>
            </div>

            <div className='overflow-x-auto'>
              <table className='w-full'>
                <thead>
                  <tr className='bg-blue-950 text-white'>
                    <th className='p-4 text-left'>Document Code</th>
                    <th className='p-4 text-left'>Document Name</th>
                    <th className='p-4 text-left'>Department</th>
                    <th className='p-4 text-left'>Revision</th>
                    <th className='p-4 text-left'>Status</th>
                  </tr>
                </thead>

                <tbody>
                  {documents.map((doc, index) => (
                    <tr key={index} className='border-b hover:bg-gray-50'>
                      <td className='p-4'>{doc.code}</td>
                      <td className='p-4'>{doc.name}</td>
                      <td className='p-4'>{doc.department}</td>
                      <td className='p-4'>{doc.revision}</td>
                      <td className='p-4'>
                        <span className='bg-green-100 text-green-700 px-4 py-1 rounded-full text-sm'>
                          {doc.status}
                        </span>
                      </td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>
          </div>

          {/* CAPA Table */}
          <div className='bg-white rounded-3xl shadow-xl p-6'>
            <div className='flex justify-between items-center mb-6'>
              <h2 className='text-2xl font-bold text-blue-950'>CAPA Tracker</h2>

              <button className='bg-red-500 text-white px-5 py-2 rounded-xl'>
                Create CAPA
              </button>
            </div>

            <div className='overflow-x-auto'>
              <table className='w-full'>
                <thead>
                  <tr className='bg-red-500 text-white'>
                    <th className='p-4 text-left'>Issue</th>
                    <th className='p-4 text-left'>Root Cause</th>
                    <th className='p-4 text-left'>Corrective Action</th>
                    <th className='p-4 text-left'>Status</th>
                  </tr>
                </thead>

                <tbody>
                  {capaData.map((item, index) => (
                    <tr key={index} className='border-b hover:bg-gray-50'>
                      <td className='p-4'>{item.issue}</td>
                      <td className='p-4'>{item.rootCause}</td>
                      <td className='p-4'>{item.action}</td>
                      <td className='p-4'>
                        <span
                          className={`px-4 py-1 rounded-full text-sm ${
                            item.status === 'Open'
                              ? 'bg-yellow-100 text-yellow-700'
                              : 'bg-green-100 text-green-700'
                          }`}
                        >
                          {item.status}
                        </span>
                      </td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>
          </div>

          {/* Footer */}
          <div className='mt-10 text-center text-gray-500'>
            © 2026 NUVITYQMS • Smart ISO • Lean • MSME Platform
          </div>
        </div>
      </div>
    </div>
  )
}
