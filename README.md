

import java.awt.EventQueue;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.KeyEvent;
import javax.swing.JButton;
import javax.swing.JCheckBoxMenuItem;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JMenu;
import javax.swing.JMenuBar;


import javax.swing.JTextField;

public class Project extends JFrame { 

	
	private static final long serialVersionUID = 3386380211796249949L;

	private static JMenuBar  menubar;
	private static JButton cal;
	public static JCheckBoxMenuItem add,sub,div,multi;

	public Project() {

		initUI();
	}

	private void initUI() {
		
//items inside the frame or window
		
		createMenuBar();
		windowitem(); 
		setTitle("Calculate");
		setSize(360, 350);
		setLocationRelativeTo(null);
		setDefaultCloseOperation(EXIT_ON_CLOSE);
	}

//window items
	
	public void windowitem() {
		setLayout(null);

		JLabel val1 = new JLabel("First  Value");
		val1.setBounds(10,10,80,30);
		add(val1);

		final JTextField value1 = new JTextField();
		value1.setBounds(100,10,160,25);
		add(value1);

		JLabel val2 = new JLabel("Second Value");
		val2.setBounds(10,40,80,25);
		add(val2);

		final JTextField value2 = new JTextField();
		value2.setBounds(100,40,160,25);
		add(value2);

		final JLabel ans = new JLabel("Answer");
		ans.setBounds(10,70,80,25);
		ans.setVisible(false);
		add(ans);

		final JTextField answer = new JTextField();
		answer.setBounds(100,70,160,25);
		answer.setVisible(false);
		add(answer);

		final JLabel ans2 = new JLabel("Answer2");
		ans2.setBounds(10,100,80,25);
		ans2.setVisible(false);
		add(ans2);
		
		final JTextField answer2 = new JTextField();
		answer2.setBounds(100,100,160,25);
		answer2.setVisible(false);
		add(answer2);
		
		final JLabel ans3 = new JLabel("Answer3");
		ans3.setBounds(10,130,80,25);
		ans3.setVisible(false);
		add(ans3);

		final JTextField answer3 = new JTextField();
		answer3.setBounds(100,130,160,25);
		answer3.setVisible(false);
		add(answer3);
		
		final JLabel ans4 = new JLabel("Answer4");
		ans4.setBounds(10,160,80,25);
		ans4.setVisible(false);
		add(ans4);
		
		final JTextField answer4 = new JTextField();
		answer4.setBounds(100,160,160,25);
		answer4.setVisible(false);
		add(answer4);
		
		cal = new JButton("Calculate");
		cal.setBounds(130,70,90,25);
		add(cal);
	
//action to be performed by the button if the checkbox is selected
		
			cal.addActionListener(new ActionListener(){

				@Override
				public void actionPerformed(ActionEvent arg0) {
					
					
					String a,b;
					a=value1.getText();
					b=value2.getText();
					double  in1, in2, ad, s, d, m ;
					in1 = Double.parseDouble(a);
					in2 = Double.parseDouble(b);
					
					ad = in1 + in2;
					s = in1 - in2;
					d = in1 * in2;
					m = in1 / in2;
					
					
					if(add.getState()==true){
						answer.setText("Sum is: "+ ad );
						ans.setVisible(true);
						ans2.setVisible(false);
						ans3.setVisible(false);
						ans4.setVisible(false);
						answer.setVisible(true);
						answer2.setVisible(false);
						answer3.setVisible(false);
						answer4.setVisible(false);
						cal.setBounds(130,100,90,25);
					}
					else if ((add.getState()==true)&&(sub.getState()==true)&& (div.getState()==false)&& (multi.getState()==false)){
						answer.setText("Sum is: " + ad );
						answer2.setText("Difference is: "+ s );
						ans.setVisible(true);
						ans2.setVisible(true);
						ans3.setVisible(false);
						ans4.setVisible(false);
						answer.setVisible(true);
						answer2.setVisible(true);
						answer3.setVisible(false);
						answer4.setVisible(false);
					}
					else if (sub.getState()==true){
						answer2.setText("Difference is: " + s );
						ans.setVisible(false);
						ans2.setVisible(true);
						ans3.setVisible(false);
						ans4.setVisible(false);
						answer.setVisible(false);
						answer2.setVisible(true);
						answer3.setVisible(false);
						answer4.setVisible(false);
						cal.setBounds(130,130,90,25);
					}
					else if (multi.getState()==true){
						answer3.setText("Pruduct is: " + m );
						ans.setVisible(false);
						ans2.setVisible(false);
						ans3.setVisible(true);
						ans4.setVisible(false);
						answer.setVisible(false);
						answer2.setVisible(false);
						answer3.setVisible(true);
						answer4.setVisible(false);
						cal.setBounds(130,160,90,25);
					}
					else if ((add.getState()==true) && (sub.getState()==true) && (div.getState()==true) && (multi.getState()==false)){
						answer.setText("Sum is: " + ad );
						answer2.setText("Difference is: "+ s );
						answer3.setText("Pruduct is: " + m );
						ans.setVisible(true);
						ans2.setVisible(true);
						ans3.setVisible(true);
						ans4.setVisible(false);
						answer.setVisible(true);
						answer2.setVisible(true);
						answer3.setVisible(true);
						answer4.setVisible(false);
					}
					else if (div.getState()==true){
						answer4.setText("Quotient is: " + d);
						ans.setVisible(false);
						ans2.setVisible(false);
						ans3.setVisible(false);
						ans4.setVisible(true);
						answer.setVisible(false);
						answer2.setVisible(false);
						answer3.setVisible(false);
						answer4.setVisible(true);
						cal.setBounds(130,190,90,25);
					}
					else if ((add.getState()==true) && (sub.getState()==true) && (div.getState()==true) && (multi.getState()==true)){
						answer.setText("Sum is: " + ad );
						answer2.setText("Difference is: "+ s );
						answer3.setText("Product is: " + m );
						answer4.setText("Quotient is: " + d);
						ans.setVisible(true);
						ans2.setVisible(true);
						ans3.setVisible(true);
						ans4.setVisible(true);
						answer.setVisible(true);
						answer2.setVisible(true);
						answer3.setVisible(true);
						answer4.setVisible(true);
					}
					else{
						answer.setText("Invalid input");
						ans.setVisible(false);
						ans2.setVisible(false);
						ans3.setVisible(false);
						ans4.setVisible(false);
						answer.setVisible(true);
						answer2.setVisible(false);
						answer3.setVisible(false);
						answer4.setVisible(false);
						cal.setBounds(130,100,90,25);
					}
				}});	
				
				
			}
// creates the menubar and the file menu containing the operations
	
	public void createMenuBar() {

//menu bar and items
		
	    menubar = new JMenuBar();
		JMenu fileMenu = new JMenu("File");
		fileMenu.setMnemonic(KeyEvent.VK_F);

		add = new JCheckBoxMenuItem("Add");
		add.setMnemonic(KeyEvent.VK_A);
		add.setSelected(false);

		sub = new JCheckBoxMenuItem("Subtract");
		sub.setMnemonic(KeyEvent.VK_S);
		sub.setSelected(false);

		multi = new JCheckBoxMenuItem("Multiply");
		multi.setMnemonic(KeyEvent.VK_M);
		multi.setSelected(false);

		div = new JCheckBoxMenuItem("Divide");
		div.setMnemonic(KeyEvent.VK_D);
		div.setSelected(false);
		
		fileMenu.add(add);
		fileMenu.add(sub);
		fileMenu.add(multi);
		fileMenu.add(div);

		menubar.add(fileMenu);	

		setJMenuBar(menubar);
	}

//main 
	public static void main(String[] args) {


		EventQueue.invokeLater(new Runnable() {

			@Override
			public void run() {
				Project ex = new Project();
				ex.setVisible(true);
			}
		});

	}


}
