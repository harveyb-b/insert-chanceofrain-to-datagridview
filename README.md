# insert-data-to-datagridview


            for (int i = 0; i < 24; i++)
            
            {
            
                long unixTimeStamp = Convert.ToInt64(data["list"][i]["dt"]);
                
                DateTime dateTime = DateTimeOffset.FromUnixTimeSeconds(unixTimeStamp).DateTime;
                

                dataGridView1.Rows[0].Cells[i].Value = dateTime.ToString("ddd, dd MMM");
                

                int precipitationPercent = (int)(100 * Convert.ToDouble(data["list"][i]["pop"]));
                
                DataGridViewCellStyle style = new DataGridViewCellStyle();
                
                style.BackColor = Color.FromArgb(200, (int)(200 * (1 - precipitationPercent / 100.0)), 255);
                
                dataGridView1.Rows[1].Cells[i].Value = $"{precipitationPercent}%";
                
                dataGridView1.Rows[1].Cells[i].Style = style;
                

                double temperature = Convert.ToDouble(data["list"][i]["main"]["temp"]);
                
                dataGridView1.Rows[2].Cells[i].Value = $"{temperature}°C";
                
            }
            

            dataGridView1.ClearSelection();
