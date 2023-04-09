# Registration-form
import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Registration implements ActionListener {
    String date[] = new String[31];
    String month[] = {"Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"};
    String years[] = new String[48];
    JFrame f = new JFrame("Registration Form");

    JButton b1 = new JButton("Submit");
    JButton b2 = new JButton("Clear");
    JCheckBox cb1 = new JCheckBox("Accept Terms and Conditions");
    JTextField t2 = new JTextField();
    JTextField t1 = new JTextField();
    JRadioButton r1 = new JRadioButton("Male");
    JRadioButton r2 = new JRadioButton("Female");
    JComboBox cm1 = new JComboBox(date);
    JComboBox cm2 = new JComboBox(month);
    JComboBox cm3 = new JComboBox(years);

    JTextArea t3 = new JTextArea();
    JLabel l5 = new JLabel("DOB");
    JLabel l4 = new JLabel("Address");
    public Registration() {
        JLabel label = new JLabel("Registration Form");

        label.setBounds(120, 20, 150, 50);
        JLabel l1  = new JLabel("Name");
        l1.setBounds(20,80,50,30);

        t1.setBounds(70,80,150,30);
        JLabel l2  = new JLabel("Mobile");
        l2.setBounds(20,112,50,30);

        t2.setBounds(70,115,150,30);
        JLabel l3 = new JLabel("Gender");
        l3.setBounds(20,145,50,30);

        r1.setBounds(80,145,70,30);
        r2.setBounds(150,145,100,30);

        l5.setBounds(20,175,50,30);

        for (int i = 0;i<31;i++)
        {
            date[i]=String.valueOf(i+1);
        }

        int year = 1975;
        for (int i =0; i<48;i++)
        {
            years[i] = String.valueOf(year);
            year = year+1;
        }

        cm1.setBounds(60,175,50,30);
        cm2.setBounds(120,175,70,30);
        cm3.setBounds(200,175,70,30);

        l4.setBounds(20,210,50,30);

        t3.setBounds(80,210,180,70);

        cb1.setBounds(40,285,200,30);

        JTextArea ta = new JTextArea();
        ta.setBounds(280,80,200,320);
        b1.setBounds(40,320,100,30);
        b2.setBounds(150,320,100,30);
        ButtonGroup b = new ButtonGroup();
        b.add(r1);b.add(r2);
        f.setSize(500, 500);
        f.add(label);
        f.add(l1);
        f.add(t1);
        f.add(l2);
        f.add(r1);
        f.add(r2);
        f.add(l3);
        f.add(t2);
        f.add(l4);
        f.add(t3);
        f.add(cb1);
        f.add(b1);
        f.add(b2);
        f.add(l5);
        f.add(cm1);
        f.add(cm2);
        f.add(cm3);
        f.add(ta);
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        f.setLayout(null);
        f.setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        if(e.getSource()==b1){
            if (cb1.isSelected()){
                String data1;
                String data
                        ="Name : "
                        + t1.getText()+"\n"+"Mobile: "+ t2.getText()+"\n";
                if(r1.isSelected())
                    data1 = "Gender : Male"+ "\n";
                else
                    data1 = "Gender : Female" + "\n";
                String data2= cm1.getSelectedItem()+"/"+cm2.getSelectedItem()+"/"+cm3.getSelectedItem()+"\n"+t3.getText();

            }
        }

    }

    public static void main(String args[])
    {
        Registration ob = new Registration();
    }
}
