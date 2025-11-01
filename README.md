# TrafficLightSimulator
import java.awt.Checkbox;
import java.awt.CheckboxGroup;
import java.awt.Color;
import java.awt.FlowLayout;
import java.awt.Font;
import java.awt.GridLayout;
import java.awt.LayoutManager;
import java.awt.event.ItemEvent;
import java.awt.event.ItemListener;

import javax.accessibility.AccessibleContext;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JLayeredPane;
import javax.swing.JMenuBar;
import javax.swing.JPanel;
import javax.swing.JRootPane;
import javax.swing.TransferHandler;

public class TrafficLightSimulator extends JFrame implements ItemListener
{
	JLabel lbl1,lbl2;
	JPanel nPanel,cPanel;
	CheckboxGroup cbg;
	
	public TrafficLightSimulator() 
	{
		setVisible(true);
		setSize(600,400);
		setTitle("Trafic Light Simulator");
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		
		setLayout(new GridLayout(2,1));
		
	    nPanel=new JPanel(new FlowLayout());
	    cPanel=new JPanel(new FlowLayout());
	    
	    
	    lbl1=new JLabel();
	    Font font=new Font("Verdana",Font.BOLD,70);
	    
	    lbl1.setFont(font);
	    nPanel.add(lbl1);
	    add(nPanel);
	    Font fontR=new Font("Verdana",Font.BOLD,20);
	    
	    lbl2=new JLabel("Select Lights");
	    lbl2.setFont(fontR);
	    cPanel.add(lbl2);
	    
	    
	    cbg=new CheckboxGroup();
	    Checkbox rbn1=new Checkbox("Red Light", cbg, false);
	    rbn1.setBackground(Color.RED);
	    rbn1.setFont(fontR);
	    cPanel.add(rbn1);
	    rbn1.addItemListener(this);
	    
	    
	    Checkbox rbn2=new Checkbox("Orange Light", cbg, false);
	    rbn2.setBackground(Color.ORANGE);
	    rbn2.setFont(fontR);
	    cPanel.add(rbn2);
	    rbn2.addItemListener(this);
	    
	    
	    Checkbox rbn3=new Checkbox("Green Light", cbg,false);
	    rbn3.setBackground(Color.GREEN);
	    rbn3.setFont(fontR);
	    cPanel.add(rbn3);
	    rbn3.addItemListener(this);
	    
	    rbn3.addItemListener(this);
	    
	    
	    add(cPanel);
	    
	}
	
	@Override
	public void itemStateChanged(ItemEvent i) 
	{
		Checkbox chk=cbg.getSelectedCheckbox();
		String str=chk.getLabel();
		char choice=str.charAt(0);
		switch(choice)
		{
		
		case 'R':lbl1.setText("STOP");
			lbl1.setForeground(Color.RED);
			break;
		case 'O':lbl1.setText("READY");
			lbl1.setForeground(Color.ORANGE);
			break;
		case 'G':lbl1.setText("GO");
			lbl1.setForeground(Color.GREEN);
			break;
		}
		
		}
		public static void main(String[] arg)
		{
			new TrafficLightSimulator();
		}
		
}
