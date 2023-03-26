# insert-chanceofrain-to-datagridview


            for (int i = 0; i < 24; i++)
            
            {

                int precipitationPercent = (int)(100 * Convert.ToDouble(data["list"][i]["pop"]));
                
                DataGridViewCellStyle style = new DataGridViewCellStyle();
                
                style.BackColor = Color.FromArgb(200, (int)(200 * (1 - precipitationPercent / 100.0)), 255);
                
                dataGridView1.Rows[1].Cells[i].Value = $"{precipitationPercent}%";
                
                dataGridView1.Rows[1].Cells[i].Style = style;
                
            }

