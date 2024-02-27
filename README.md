# Подсказочки

## Учитывать регистр в таблице
```
ALTER TABLE AuthAcc 
ALTER COLUMN PasswordAcc nvarchar(20) 
COLLATE SQL_Latin1_General_CP1_CS_AS
```

## DataGrid
```
 <DataGrid.Columns>
     <DataGridTextColumn Header="Id" Binding="{Binding IdUser}"/>
       <DataGridTextColumn Header="role" Binding="{Binding UserRole.RoleName}"/>
```

## Отображение данных из бд
```
SqlCommand cmd = new SqlCommand("select * from TestTable", con);
DataTable dt = new DataTable();
SqlDataAdapter adapter = new SqlDataAdapter(cmd);
adapter.Fill(dt);
DT.ItemsSource = dt.DefaultView;
or
Users_DT.ItemsSource = AppConnect.modelOdb.UserInfo.ToList();
```

## del data
```
delete UserInfo where IdUser between 7 and 7
DataRowView drv = (DataRowView)DT.SelectedItem;
```

## update data
```
 SqlCommand cmd = new SqlCommand($"update TestTable set Descr='{TXB.Text}' where Id={_id}", conn);
 cmd.ExecuteNonQuery();
```

 ## insert data 
 ```
 SqlCommand Com(string cmdText)
{
    SqlCommand cmd = new SqlCommand(cmdText, Connection());
    cmd.ExecuteNonQuery();
    return cmd;
}
 Com($"insert into TestTable (Descr) values ('{Descr_TXB.Text}')");
```
 ## search data
  ```
DataTable dt = new DataTable();
var cmd = Com($"select * from TestTable where Descr LIKE '{Search_TXB.Text}%'");
SqlDataAdapter adapter = new SqlDataAdapter(cmd);
adapter.Fill(dt);
DT.ItemsSource = dt.DefaultView;
```

