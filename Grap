import React, { useState } from 'react';
import { Card, CardHeader, CardTitle, CardContent } from '@/components/ui/card';
import { BarChart, Bar, XAxis, YAxis, Tooltip, Legend, ResponsiveContainer } from 'recharts';

const RestaurantRevenueDashboard = () => {
  const [restaurants, setRestaurants] = useState([
    {
      name: 'ร้านอาหารครัวคุณแม่',
      monthlyData: [
        { month: 'มกราคม', รายรับ: 215000, ค่าใช้จ่าย: 155000 },
        { month: 'กุมภาพันธ์', รายรับ: 225000, ค่าใช้จ่าย: 160000 },
        { month: 'มีนาคม', รายรับ: 245000, ค่าใช้จ่าย: 170000 },
        { month: 'เมษายน', รายรับ: 235000, ค่าใช้จ่าย: 165000 },
        { month: 'พฤษภาคม', รายรับ: 255000, ค่าใช้จ่าย: 180000 }
      ]
    },
    {
      name: 'ร้านอาหารครัวไทย',
      monthlyData: [
        { month: 'มกราคม', รายรับ: 260000, ค่าใช้จ่าย: 185000 },
        { month: 'กุมภาพันธ์', รายรับ: 280000, ค่าใช้จ่าย: 200000 },
        { month: 'มีนาคม', รายรับ: 295000, ค่าใช้จ่าย: 210000 },
        { month: 'เมษายน', รายรับ: 275000, ค่าใช้จ่าย: 195000 },
        { month: 'พฤษภาคม', รายรับ: 310000, ค่าใช้จ่าย: 220000 }
      ]
    },
    {
      name: 'ร้านก๋วยเตี๋ยวต้นตำรับ',
      monthlyData: [
        { month: 'มกราคม', รายรับ: 185000, ค่าใช้จ่าย: 135000 },
        { month: 'กุมภาพันธ์', รายรับ: 195000, ค่าใช้จ่าย: 140000 },
        { month: 'มีนาคม', รายรับ: 205000, ค่าใช้จ่าย: 150000 },
        { month: 'เมษายน', รายรับ: 190000, ค่าใช้จ่าย: 145000 },
        { month: 'พฤษภาคม', รายรับ: 215000, ค่าใช้จ่าย: 160000 }
      ]
    }
  ]);

  const calculateTotalStats = () => {
    let totalRevenue = 0;
    let totalExpense = 0;
    let totalProfit = 0;

    restaurants.forEach(restaurant => {
      restaurant.monthlyData.forEach(monthData => {
        totalRevenue += monthData.รายรับ;
        totalExpense += monthData.ค่าใช้จ่าย;
        totalProfit += monthData.รายรับ - monthData.ค่าใช้จ่าย;
      });
    });

    return { totalRevenue, totalExpense, totalProfit };
  };

  const stats = calculateTotalStats();

  return (
    <div className="bg-orange-50 min-h-screen p-6">
      <Card className="bg-white shadow-lg rounded-lg">
        <CardHeader className="bg-orange-500 text-white py-4">
          <CardTitle className="text-2xl font-bold">📊 รายรับร้านอาหารทั้งหมด</CardTitle>
        </CardHeader>
        <CardContent className="p-6">
          <div className="grid grid-cols-3 gap-4 mb-6">
            <div className="bg-orange-100 p-4 rounded-lg">
              <h3 className="text-orange-700 font-semibold">รายรับรวม</h3>
              <p className="text-xl font-bold text-orange-900">
                {stats.totalRevenue.toLocaleString()} บาท
              </p>
            </div>
            <div className="bg-orange-100 p-4 rounded-lg">
              <h3 className="text-orange-700 font-semibold">ค่าใช้จ่ายรวม</h3>
              <p className="text-xl font-bold text-orange-900">
                {stats.totalExpense.toLocaleString()} บาท
              </p>
            </div>
            <div className="bg-orange-100 p-4 rounded-lg">
              <h3 className="text-orange-700 font-semibold">กำไรสุทธิ</h3>
              <p className="text-xl font-bold text-green-700">
                {stats.totalProfit.toLocaleString()} บาท
              </p>
            </div>
          </div>

          {restaurants.map((restaurant, index) => (
            <div key={index} className="mb-8">
              <h2 className="text-xl font-bold text-orange-700 mb-4">{restaurant.name}</h2>
              <ResponsiveContainer width="100%" height={300}>
                <BarChart data={restaurant.monthlyData}>
                  <XAxis dataKey="month" stroke="#FF8C00" />
                  <YAxis stroke="#FF8C00" />
                  <Tooltip 
                    contentStyle={{ backgroundColor: '#FFF3E0', borderColor: '#FF8C00' }}
                    labelStyle={{ color: '#D35400' }}
                  />
                  <Legend />
                  <Bar dataKey="รายรับ" name="รายรับ" fill="#FF8C00" barSize={30} />
                  <Bar dataKey="ค่าใช้จ่าย" name="ค่าใช้จ่าย" fill="#FFA500" barSize={30} />
                </BarChart>
              </ResponsiveContainer>
            </div>
          ))}
        </CardContent>
      </Card>
    </div>
  );
};

export default RestaurantRevenueDashboard;
