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

       
       

        }
    }
    }
    

