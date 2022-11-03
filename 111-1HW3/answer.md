# 第3次作業-作業-HW3
>
>學號：109111139
><br />
>姓名：繆昊廷
><br />
>作業撰寫時間：65mins
><br />
>最後撰寫文件日期：2022/11/03
>

本份文件包含以下主題：(至少需下面兩項，若是有多者可以自行新增)
- [x]說明內容
- [x]個人認為完成作業須具備觀念

## 說明程式與內容


下段程式碼則為使用後結果：第一個下拉式選單顯示蔬菜和水果，若選擇蔬菜，則第二個下拉式選單顯示A菜和空心菜，若選擇水果，則顯示番茄和火龍果。

```csharp
string[] Category = new string[2] { "蔬菜", "水果" };
string[,] Food = new string[2,2] { { "A菜", "空心菜" },{ "番茄", "火龍果" } };
        protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                for (int i = 0; i < Category.Length; i++)
                {
                    ListItem o_L = new ListItem();
                    o_L.Text = Category[i];
                    o_L.Value = Category[i];
                    ddl_Category.Items.Add(o_L);
                }
                second_list();
            }
            
        }

        protected void second_list()
        {
            int a = ddl_Category.SelectedIndex;
            ddl_Food.Items.Clear();
            for(int i = 0;i < Food.GetLength(1); i++)
            {
                ListItem o_L = new ListItem();
                o_L.Text = Food[a,i];
                o_L.Value = Food[a,i];
                ddl_Food.Items.Add(o_L);
            }
        }

        protected void ddl_Category_SelectedIndexChanged(object sender, EventArgs e)
        {
            second_list();
        }
```


下段程式碼則為使用後結果：建立兩個下拉式選單

```html
<%@ Page Language="C#" AutoEventWireup="true" ...>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<meta http-equiv="Content-Type" ...>
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        <asp:DropDownList ID="ddl_Category" runat="server" AutoPostBack="True" OnSelectedIndexChanged="ddl_Category_SelectedIndexChanged"></asp:DropDownList>
            <asp:DropDownList ID="ddl_Food" runat="server"></asp:DropDownList>
        </div>
    </form>
</body>
</html>
```


## 個人認為完成作業須具備觀念

如何用陣列和for迴圈將下拉式選單的內容顯示出來，還可以透過第一個下拉式選單來決定第二個下拉式選單要顯示什麼。

