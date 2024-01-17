public class FormDienThoai extends javax.swing.JFrame {

    private ArrayList<DienThoai> dsDienThoai;
    public FormDienThoai() {
        dsDienThoai = new ArrayList<>();
        initComponents();
        this.setLocationRelativeTo(null);
    }
 private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // them
        
        DienThoai dt = new DienThoai();
        
        dt.setTenHang(jtenhang.getText());
        dt.setMaHang(jmahang.getText());
        dt.setMauSac(jmausac.getText());
        dt.setDungLuongBoNho(jdungl.getText());
        dt.setGiaBan(jgiaban.getText());
        dt.setNhaSanXuat(jnhasx.getText());
        dsDienThoai.add(dt);
        
        JOptionPane.showMessageDialog(rootPane, "Da them");
        for (DienThoai dienThoai : dsDienThoai) {
            dienThoai.hienThiTT();
        }
    }                                        

    private void jButton2ActionPerformed(java.awt.event.ActionEvent evt) {                                         
       //luu
        File file = new File("dienthoai.dat");
        try {
            PrintWriter printWriter = new PrintWriter(file);
            
            for (DienThoai dienThoai : dsDienThoai) {
                printWriter.println(dienThoai.hienThi());
            }
            printWriter.close();
            
        } catch (FileNotFoundException ex) {
           
        }
        JOptionPane.showMessageDialog(rootPane, "da luu");
    }                                   
