using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using Telegram.Bot;
using Telegram.Bot.Types;
using Telegram.Bot.Types.Enums;
using static System.Windows.Forms.VisualStyles.VisualStyleElement;
using System.Net.Http;

namespace PRACTIKA
{
    public partial class Form1 : Form
    {
        private DataTable scheduleTable;
        public Form1()
        {
            InitializeComponent();
            InitializeData();
        }
        private void InitializeData()
        {
            scheduleTable = new DataTable();
            scheduleTable.Columns.Add("ID", typeof(int));
            scheduleTable.Columns.Add("Группа", typeof(string));
            scheduleTable.Columns.Add("Дата публикации", typeof(DateTime));
            scheduleTable.Columns.Add("Статус", typeof(string));
            LoadData();
            dataGridView1.DataSource = scheduleTable;
            dataGridView1.Font = new Font("Times New Roman", 14);
            dataGridView1.AutoSizeColumnsMode = DataGridViewAutoSizeColumnsMode.AllCells;
            dataGridView1.AllowUserToAddRows = false;
            if (dataGridView1.Columns.Contains("Статус"))
            {
                dataGridView1.Columns["Статус"].DefaultCellStyle.Alignment =
                    DataGridViewContentAlignment.MiddleCenter;
            }
            if (button1 != null)
            {
                button1.Click += button1_Click;
            }
        }
        private void LoadData()
        {
            scheduleTable.Rows.Add(1, "Мемы", new DateTime(2024, 12, 9), "✅ Опубликовано");
            scheduleTable.Rows.Add(2, "Новости", new DateTime(2024, 12, 12), "✅ Опубликовано");
            scheduleTable.Rows.Add(3, "Крипта", new DateTime(2024, 12, 15), "✅ Опубликовано");
            scheduleTable.Rows.Add(4, "Финансы", new DateTime(2024, 12, 18), "⏳ Ожидает");
            scheduleTable.Rows.Add(5, "Спорт", new DateTime(2024, 12, 21), "⏳ Ожидает");
            scheduleTable.Rows.Add(6, "Кулинария", new DateTime(2024, 12, 24), "⏳ Ожидает");
            scheduleTable.Rows.Add(7, "Авто", new DateTime(2024, 12, 26), "⏳ Ожидает");
            scheduleTable.Rows.Add(8, "Игры", new DateTime(2024, 12, 28), "⏳ Ожидает");
            scheduleTable.Rows.Add(9, "Кино", new DateTime(2024, 12, 30), "⏳ Ожидает");
            scheduleTable.Rows.Add(10, "Музыка", new DateTime(2024, 12, 31), "⏳ Ожидает");
        }
        private void button1_Click(object sender, EventArgs e)
        {
            if (dataGridView1.SelectedRows.Count > 0)
            {
                foreach (DataGridViewRow row in dataGridView1.SelectedRows)
                {
                    if (row.Cells["Статус"].Value.ToString() == "⏳ Ожидает")
                    {
                        row.Cells["Статус"].Value = "✅ Опубликовано";
                    }
                }
            }
            dataGridView1.Invalidate();
            dataGridView1.Update();
        }
        private void textBox1_TextChanged(object sender, EventArgs e)
        {
            ((DataTable)dataGridView1.DataSource).DefaultView.RowFilter = $"Группа LIKE '%{textBox1.Text}%'";
        }
    }
}
