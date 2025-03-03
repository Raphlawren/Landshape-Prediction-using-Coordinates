 # Prophet-Prediction
Predicting the future coordinates of a shape using PROPHET in python

Here is the view of all the shapes of the intersections for 6 years.
![Screenshot 2025-03-03 at 12 53 09 AM](https://github.com/user-attachments/assets/378c6772-f483-45ca-adff-dde3f95ba4dc)


This is the result when i predicted using prophet, the results came in points\
![Screenshot 2025-03-03 at 12 55 10 AM](https://github.com/user-attachments/assets/4bd25399-2c6e-444d-b936-67d7bf6eede3)

Then i used the preprocessing toolbox to convert "points to path"

![Screenshot 2025-03-03 at 12 56 14 AM](https://github.com/user-attachments/assets/3e8418dc-cc6c-4884-b806-add936180723)

I then converted the lines to polygon by clicking Vector > Geometry Tools > Lines to Polygons\
![Screenshot 2025-03-03 at 12 59 05 AM](https://github.com/user-attachments/assets/7b3a7fa0-f7e9-4c00-a549-2034ace4f545)

The issue i think i have is: \
The predicted shape/coordinate is smaller. 
I think when the model are being trained, it reduced the values for better training which affected the result. 
![Screenshot 2025-03-03 at 1 01 04 AM](https://github.com/user-attachments/assets/b1081fef-9c06-4e55-9429-6ccad6729a8e)

I compared the min and max of the original data with the predicted data\ sheet 1 represents x_coord and the sheet 2 represents the y_coord. The gap in the value of the min in the x_coord is a little much, likewise for the y_coord.\
![Screenshot 2025-03-03 at 2 20 25 AM](https://github.com/user-attachments/assets/cbe37101-55a9-45c5-bd36-940aeed004f9)

I then implemented the min-max rescaling by using this formlular \
x_pred_scaled = ((x_pred - x_pred.min()) / (x_pred.max() - x_pred.min())) * (x_orig.max() - x_orig.min()) + x_orig.min()\
y_pred_scaled = ((y_pred - y_pred.min()) / (y_pred.max() - y_pred.min())) * (y_orig.max() - y_orig.min()) + y_orig.min()

In the image below, the min and the max value of the predicted data matches the original data. \
![Screenshot 2025-03-03 at 2 32 01 AM](https://github.com/user-attachments/assets/88aa393b-de23-4604-b42c-6e734aa0bdb8)

In the image below is the shape of the old and the reshaped predicted shape.\
![Screenshot 2025-03-03 at 2 36 19 AM](https://github.com/user-attachments/assets/06750836-81cb-45d3-848d-d9b6dec5275e)\

we can see that the reshaped predicted shape is bigger.

![Screenshot 2025-03-03 at 2 51 35 AM](https://github.com/user-attachments/assets/3c0141dd-862f-4469-8960-020b8f09bdb7)

After I compared the predicted shape with the old shapes, I observed it fits the first 3 shape better\

![Screenshot 2025-03-03 at 2 54 50 AM](https://github.com/user-attachments/assets/d70fc7dc-780a-44bf-95ea-020c523d346b)

View on showing the 6 shapes over time with the predicted shape \
![Screenshot 2025-03-03 at 2 57 02 AM](https://github.com/user-attachments/assets/dc38f2b5-53c2-43e9-974d-4ffcd463e5ad)


I think that the inbalance in the shape massive increament from the 4th to the 6th shape might have caused the imperfection.
