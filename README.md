# Connect
This project is connect SQL server and C#

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Data.SqlClient;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using static System.Windows.Forms.VisualStyles.VisualStyleElement;


namespace WindowsFormsApp1
{
    public partial class Form2 : Form
    {
        public Form2()

        {
            
            InitializeComponent();
        }
        SqlConnection conn;
        private void button3_Click(object sender, EventArgs e)
        {
          this.Hide();
            Login2 k =new Login2();
            k.Show(); 
        }

        private void label1_Click(object sender, EventArgs e)
        {

        }

        private void button1_Click(object sender, EventArgs e)
        {
            textBox1.Text = string.Empty;
            textBox2.Text = string.Empty;
            textBox3.Text = string.Empty;
            textBox4.Text = string.Empty;
            textBox5.Text = string.Empty;
        }

        private void button2_Click(object sender, EventArgs e)
        {
            connect();
        }
        private void connect()
        {
            string constr = "Data Source = DESKTOP-UOO72VA\\SQLEXPRESS; Initial Catalog =HIRIG_SYSTEM;Integrated Security = SSPI";
            conn = new SqlConnection(constr);
            conn.Open();
            //con.Close();
            //MessageBox.Show("sucessfully connection Cadde!");
        }

        private void button4_Click(object sender, EventArgs e)
        {
            try
            {
                connect();
                string gelinta_xog = "insert into User_registartion values ('" + textBox1.Text + "','" + textBox2.Text + "','" + textBox3.Text + "','" + textBox4.Text + "','" + textBox5.Text + "')";
                SqlCommand cmd = new SqlCommand(gelinta_xog, conn);
                cmd.ExecuteNonQuery();
                MessageBox.Show("successfully your Account ");
                textBox1.Text = string.Empty;
                textBox2.Text = string.Empty;
                textBox3.Text = string.Empty;
                textBox4.Text = string.Empty;
                textBox5.Text = string.Empty;
            }
            catch(Exception ex){
                MessageBox.Show(ex.Message);
            }

        }

        private void button2_Click_1(object sender, EventArgs e)
        {
            connect();
        }

        private void textBox2_TextChanged(object sender, EventArgs e)
        {

        }

        private void Form2_Load(object sender, EventArgs e)
        {

        }
    }
    }
    

