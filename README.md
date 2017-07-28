package Handler;

import Model.*;
import DBM.*;
import javax.swing.*;

public class ProjectViewerHandler
{
    ProjectList pm ;
    DatabaseManager db;
    ProjectListQuery prj;
    
    public ProjectViewerHandler()
    {
        pm = new ProjectList();
        db = new DatabaseManager();
        prj = new ProjectListQuery();
    }
   
    public void processProjectList()
    {
        try
        {
            String dataReceived = db.getData(prj.getProjectListQuery(),4);
            String dataToArray[] = dataReceived.split(";");
            String tableData[][] = new String[dataToArray.length / 4][4];
            int arrayDataIndex = 0;
            for(int x = 0; x < dataToArray.length / 4; x ++)
            {
                for(int y = 0; y < 4; y ++)
                {
                    tableData[x][y] = dataToArray[arrayDataIndex];
                    arrayDataIndex ++;
                }
            }
            pm.setProjectList(tableData);
        }
        catch(Exception e)
        {
            JOptionPane.showMessageDialog(null, "Could not retrieve data!", "ERROR", JOptionPane.ERROR_MESSAGE);//Display the error occured
        }
    }
    
    public void processProjectListByID(String ID)throws Exception
    {
        try
        {
            String dataReceived = db.getData(prj.getProjectList_IDQuery(ID),4);
            String dataToArray[] = dataReceived.split(";");
            String tableData[][] = new String[dataToArray.length / 4][4];
            int arrayDataIndex = 0;
            for (int x = 0; x < dataToArray.length / 4; x++)
            {
                for(int y = 0; y < 4; y ++)
                {
                    tableData[x][y] = dataToArray[arrayDataIndex];
                    arrayDataIndex ++;
                }
            }
            pm.setProjectList(tableData);
        }
        catch(Exception e)
        {
            JOptionPane.showMessageDialog(null, "Could not retrieve data!", "ERROR", JOptionPane.ERROR_MESSAGE);//Display the error occured
        }
    }
    
    public void processProjectListByCommonName(String CommonName)throws Exception
    {
        try
        {
            String dataReceived = db.getData(prj.getProjectList_CommonNameQuery(CommonName),4);
            String dataToArray[] = dataReceived.split(";");
            String tableData[][] = new String[dataToArray.length / 4][4];
            int arrayDataIndex = 0;
            for(int x = 0; x < dataToArray.length / 4; x ++)
            {
                for(int y = 0; y < 4; y ++)
                {
                    tableData[x][y] = dataToArray[arrayDataIndex];
                    arrayDataIndex ++;
                }
            }
            pm.setProjectList(tableData);
        }
        catch(Exception e)
        {
            JOptionPane.showMessageDialog(null, "Could not retrieve data!", "ERROR", JOptionPane.ERROR_MESSAGE);//Display the error occured
        }
    }
    
    public void processProjectListByProjectName(String ProjectName)throws Exception
    {
        try
        {
            String dataReceived = db.getData(prj.getProjectList_ProjectNameQuery(ProjectName),4);
            String dataToArray[] = dataReceived.split(";");
            String tableData[][] = new String[dataToArray.length / 4][4];
            int arrayDataIndex = 0;
            for(int x = 0; x < dataToArray.length / 4; x ++)
            {
                for(int y = 0; y < 4; y ++)
                {
                    tableData[x][y] = dataToArray[arrayDataIndex];
                    arrayDataIndex ++;
                }
            }
            pm.setProjectList(tableData);
        }
        catch(Exception e)
        {
            JOptionPane.showMessageDialog(null, "Could not retrieve data!", "ERROR", JOptionPane.ERROR_MESSAGE);//Display the error occured
        }
    }
    
    public void processProjectListByManager(String Manager)throws Exception
    {
        try
        {
            String dataReceived = db.getData(prj.getProjectList_ManagerQuery(Manager),4);
            String dataToArray[] = dataReceived.split(";");
            String tableData[][] = new String[dataToArray.length / 4][4];
            int arrayDataIndex = 0;
            for(int x = 0; x < dataToArray.length / 4; x ++)
            {
                for(int y = 0; y < 4; y ++)
                {
                    tableData[x][y] = dataToArray[arrayDataIndex];
                    arrayDataIndex ++;
                }
            }
            pm.setProjectList(tableData);
        }
        catch(Exception e)
        {
            JOptionPane.showMessageDialog(null, "Could not retrieve data!", "ERROR", JOptionPane.ERROR_MESSAGE);//Display the error occured
        }
    }
    
    public String[][] returnProjectList()
    {
        return pm.getProjectList();
    }
    
}
