import java.util.Random;

import java.awt.BorderLayout;
import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JButton;
import java.awt.List;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import java.awt.Color;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
public class say extends JFrame {

	/**
	 * 
	 */
	private static final long serialVersionUID = 1L;
	private JPanel contentPane;

	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					say frame = new say();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public say() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 400, 400);
		contentPane = new JPanel();
		contentPane.setBackground(Color.GREEN);
		contentPane.setForeground(Color.RED);
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		List list = new List();
		list.setBounds(56, 133, 113, 197);
		contentPane.add(list);
		
		List list_1 = new List();
		list_1.setBounds(228, 133, 113, 197);
		contentPane.add(list_1);
		
		JButton btnNewButton = new JButton("SAYI ÜRET");
		btnNewButton.setBounds(105, 5, 188, 73);
		btnNewButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				Random random = new Random();
				int sayi = random.nextInt(100);
				String sayi1 = Integer.toString(sayi);
				if(sayi > 50) {
					list.add(sayi1);
						
				}
				else if (sayi<50) {
					list_1.add(sayi1);
				}
				if(sayi==50) {
					JOptionPane.showMessageDialog(null,"SAYI 50'YE EŞİTTİR");
				}
			}
		});
		
		
		contentPane.add(btnNewButton);
		
		JLabel lblX = new JLabel("SAYI 50'DEN KÜÇÜKTÜR ");
		lblX.setBounds(56, 99, 152, 28);
		contentPane.add(lblX);
		
		JLabel lblX_1 = new JLabel("SAYI 50'DEN BÜYÜKTÜR");
		lblX_1.setBounds(218, 107, 156, 13);
		contentPane.add(lblX_1);
		
	}
}
