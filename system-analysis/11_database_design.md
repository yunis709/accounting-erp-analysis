# 11. تصميم قاعدة البيانات (Database Design)

## الكيانات الرئيسية والجداول

| الكيان      | أهم الحقول            | وصف العلاقة                               |
|-------------|----------------------|-------------------------------------------|
| Customers   | id, name, phone, ... | مرتبط بـ Invoices, Payments, Branches     |
| Suppliers   | id, name, contact... | مرتبط بـ Purchases, Payments              |
| Products    | id, name, barcode... | مرتبط بـ Categories, Invoices, Stock      |
| Categories  | id, name             | مرتبط بـ Products                         |
| Invoices    | id, type, date...    | مرتبط بـ Customers, InvoiceItems          |
| InvoiceItems| id, invoice_id, ...  | مرتبط بفواتير ومخزون                      |
| Accounts    | id, name, number...  | عمود محوري للقيود اليومية                 |
| JournalEntries | id, date, ...     | لكل عملية مالية (بيع/شراء/سداد/تسوية)     |
| Warehouses  | id, name, branch...  | يدير المخزون لكل فرع/مخزن                 |
| StockMovements| id, product, qty   | يخزن كل حركة المخزون                      |
| Users       | id, username, role...| صلاحيات النظام                            |

## مخطط ERD نصي رئيسي
```
[Customers]---<Invoices>---<InvoiceItems>---[Products]---<StockMovements>---[Warehouses]
           |                                      
      [Payments]                              
           |  
      [JournalEntries]
```
