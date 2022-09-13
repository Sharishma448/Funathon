# Funathon
package P1;
import java.awt.EventQueue;

import javax.swing.JFrame;
import java.awt.Color;
import javax.swing.JLabel;
import javax.swing.JOptionPane;

import java.awt.Font;
import javax.swing.JComboBox;
import javax.swing.DefaultComboBoxModel;
import javax.swing.DefaultListModel;
import javax.swing.JTextField;
import javax.swing.JButton;
import java.awt.event.ActionListener;
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.awt.event.ActionEvent;
import javax.swing.ButtonGroup;


public class GamesWebsite {
	private JFrame frame;
	private JTextField textField;
	private final ButtonGroup buttonGroup = new ButtonGroup();
	DefaultListModel<String> Model_Items=new DefaultListModel<String>();
	DefaultListModel<Integer> Model_Quantity=new DefaultListModel<Integer>();


	/**
	 * Launch the application.
	 */


	public static void main(String[] args) {
		// TODO Auto-generated method stub
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					GamesWebsite window = new GamesWebsite();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the application.
	 */
	public GamesWebsite() {
		initialize();
	}

	/**
	 * Initialize the contents of the frame.
	 */
	private void initialize() {
		frame = new JFrame();
		frame.getContentPane().setBackground(Color.CYAN);
		frame.setBounds(100, 100, 1088, 705);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.getContentPane().setLayout(null);
		
		JLabel lblNewLabel = new JLabel("GAME  WEBSITE");
		lblNewLabel.setFont(new Font("Times New Roman", Font.BOLD, 45));
		lblNewLabel.setBounds(314, 29, 403, 53);
		frame.getContentPane().add(lblNewLabel);
		
		JLabel lblNewLabel_1 = new JLabel("GAME TYPE");
		lblNewLabel_1.setFont(new Font("Times New Roman", Font.BOLD, 21));
		lblNewLabel_1.setBounds(125, 126, 144, 39);
		frame.getContentPane().add(lblNewLabel_1);
		
		JLabel lblNewLabel_1_1 = new JLabel("TITLE NAME");
		lblNewLabel_1_1.setFont(new Font("Times New Roman", Font.BOLD, 21));
		lblNewLabel_1_1.setBackground(Color.ORANGE);
		lblNewLabel_1_1.setBounds(728, 126, 144, 39);
		frame.getContentPane().add(lblNewLabel_1_1);
		
		JLabel lblNewLabel_1_2 = new JLabel("OPERATING SYSTEM");
		lblNewLabel_1_2.setFont(new Font("Times New Roman", Font.BOLD, 21));
		lblNewLabel_1_2.setBounds(87, 250, 221, 39);
		frame.getContentPane().add(lblNewLabel_1_2);
		
		JLabel lblNewLabel_1_3 = new JLabel("RAM SIZE");
		lblNewLabel_1_3.setFont(new Font("Times New Roman", Font.BOLD, 21));
		lblNewLabel_1_3.setBounds(728, 250, 144, 39);
		frame.getContentPane().add(lblNewLabel_1_3);
		
		JComboBox comboBox = new JComboBox();
		comboBox.setFont(new Font("Trebuchet MS", Font.BOLD, 20));
		comboBox.setBackground(Color.PINK);
		comboBox.setModel(new DefaultComboBoxModel(new String[] {"CAR RACING", "WORD FIND", "BATTLEGROUNDS", "SHOOTING", "PUZZLES", "VIDEO GAMES"}));
		comboBox.setBounds(38, 179, 342, 39);
		frame.getContentPane().add(comboBox);
		
		textField = new JTextField();
		textField.setBackground(Color.PINK);
		textField.setBounds(546, 182, 342, 39);
		frame.getContentPane().add(textField);
		textField.setColumns(10);
		
		JComboBox comboBox_1 = new JComboBox();
		comboBox_1.setFont(new Font("Times New Roman", Font.BOLD, 21));
		comboBox_1.setModel(new DefaultComboBoxModel(new String[] {"WINDOWS10", "WINDOWS11"}));
		comboBox_1.setBackground(Color.PINK);
		comboBox_1.setBounds(38, 326, 342, 36);
		frame.getContentPane().add(comboBox_1);
		
		JComboBox comboBox_2 = new JComboBox();
		comboBox_2.setFont(new Font("Times New Roman", Font.BOLD, 21));
		comboBox_2.setModel(new DefaultComboBoxModel(new String[] {"4", "8", "12", "16", "32"}));
		comboBox_2.setBackground(Color.PINK);
		comboBox_2.setBounds(546, 325, 342, 39);
		frame.getContentPane().add(comboBox_2);
		
		JLabel lblNewLabel_1_3_1 = new JLabel("GRAPHICS CARD");
		lblNewLabel_1_3_1.setFont(new Font("Times New Roman", Font.BOLD, 21));
		lblNewLabel_1_3_1.setBounds(415, 406, 144, 39);
		frame.getContentPane().add(lblNewLabel_1_3_1);
		
		JComboBox comboBox_3 = new JComboBox();
		comboBox_3.setModel(new DefaultComboBoxModel(new String[] {"NVIDIA GeForce GTX 1050 Ti(_4GB_)", "NVIDIA GeForce GTX 1060 (_16GB_)", "NVIDIA GeForce GTX 970(_8GB_)", "NVIDIA GeForce GTX 1060 (_12GB_)", ""}));
		comboBox_3.setFont(new Font("Times New Roman", Font.BOLD, 21));
		comboBox_3.setBackground(Color.PINK);
		comboBox_3.setBounds(280, 456, 397, 39);
		frame.getContentPane().add(comboBox_3);
		
		JButton btnNewButton = new JButton("ADD GAME");
		btnNewButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				try  
				{
					FileWriter FW=new FileWriter("C:\\Users\\sriya\\OneDrive\\Desktop\\ctod\\Projects\\Games.txt",true);
					BufferedWriter SB=new BufferedWriter(FW);
					FW.append(comboBox.getSelectedItem().toString() +",");
					FW.append(textField.getText() +",");
					FW.append(comboBox_1.getSelectedItem().toString() +",");
					FW.append(comboBox_2.getSelectedItem().toString() +",");
					FW.append(comboBox_3.getSelectedItem().toString() +",");
					FW.flush();
					FW.close();
				}
				catch(IOException E)
				{
					
				}
			}
		});
		buttonGroup.add(btnNewButton);
		btnNewButton.setBackground(Color.MAGENTA);
		btnNewButton.setFont(new Font("Times New Roman", Font.BOLD, 21));
		btnNewButton.setBounds(38, 556, 187, 53);
		frame.getContentPane().add(btnNewButton);
		
		JButton btnRemoveGame = new JButton("REMOVE GAME");
		btnRemoveGame.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				try  
				{
					FileWriter FW=new FileWriter("C:\\SAMPLE\\GAME_WEB.csv",true);
					BufferedWriter SB=new BufferedWriter(FW);
					comboBox.setSelectedIndex(0);
					textField.setText(null);
					comboBox_1.setSelectedIndex(0);
					comboBox_2.setSelectedIndex(0);
					comboBox_3.setSelectedIndex(0);
					FW.flush();
					FW.close();
				}
				catch(IOException E)
				{
					
				}
				/*comboBox.setSelectedIndex(0);
				textField.setText(null);
				comboBox_1.setSelectedIndex(0);
				comboBox_2.setSelectedIndex(0);
				comboBox_3.setSelectedIndex(0);*/
				
			}
		});
		buttonGroup.add(btnRemoveGame);
		btnRemoveGame.setBackground(Color.MAGENTA);
		btnRemoveGame.setFont(new Font("Times New Roman", Font.BOLD, 21));
		btnRemoveGame.setBounds(250, 556, 216, 53);
		frame.getContentPane().add(btnRemoveGame);
		
		JButton btnSubmit = new JButton("SUBMIT");
		btnSubmit.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				String gtyp=comboBox.getSelectedItem().toString();
				String tnam=textField.getText();
				String opsy=comboBox_1.getSelectedItem().toString();
				String rs=comboBox_2.getSelectedItem().toString();
				String gc=comboBox_3.getSelectedItem().toString();
				if(textField.getText().isEmpty())
				{
					JOptionPane.showMessageDialog(btnSubmit, "Enter the TITLE NAME of the game");
				}
				try  
				{
					FileWriter FW=new FileWriter("C:\\SAMPLE\\GAME_WEB.csv",true);
					BufferedWriter SB=new BufferedWriter(FW);
					FW.append(comboBox.getSelectedItem().toString());
					FW.append(textField.getText());
					FW.append(comboBox_1.getSelectedItem().toString());
					FW.append(comboBox_2.getSelectedItem().toString());
					FW.append(comboBox_3.getSelectedItem().toString());
					FW.flush();
					FW.close();
				}
				catch(IOException E)
				{
					
				}
					JOptionPane.showMessageDialog(btnSubmit, " SUCCESSFULLY COMPLETED ");
			}
		});
		btnSubmit.setBackground(Color.GREEN);
		btnSubmit.setFont(new Font("Times New Roman", Font.BOLD, 25));
		btnSubmit.setBounds(701, 555, 187, 53);
		frame.getContentPane().add(btnSubmit);
		
		JButton btnClear = new JButton("CLEAR");
		btnClear.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				comboBox.getSelectedItem();
				textField.setText(null);
				comboBox_1.getSelectedItem();
				comboBox_2.getSelectedItem();
				comboBox_3.getSelectedItem();
				
			}
		});
		btnClear.setBackground(Color.YELLOW);
		btnClear.setFont(new Font("Times New Roman", Font.BOLD, 21));
		btnClear.setBounds(494, 556, 187, 53);
		frame.getContentPane().add(btnClear);
	


	}

}
