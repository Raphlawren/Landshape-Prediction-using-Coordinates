# Prophet-Prediction
Predicting the future coordinates of a shape using PROPHET in python\

Here is the view of all the shapes of the intersections for 6 years.
![Screenshot 2025-03-03 at 12 53 09 AM](https://github.com/user-attachments/assets/378c6772-f483-45ca-adff-dde3f95ba4dc)


This is the result when i predicted using prophet, the results came in points\
![Screenshot 2025-03-03 at 12 55 10 AM](https://github.com/user-attachments/assets/4bd25399-2c6e-444d-b936-67d7bf6eede3)

Then i used the preprocessing toolbox to convert "points to path"\

![Screenshot 2025-03-03 at 12 56 14 AM](https://github.com/user-attachments/assets/3e8418dc-cc6c-4884-b806-add936180723)

I then converted the lines to polygon by clicking Vector > Geometry Tools > Lines to Polygons\
![Screenshot 2025-03-03 at 12 59 05 AM](https://github.com/user-attachments/assets/7b3a7fa0-f7e9-4c00-a549-2034ace4f545)

The issue i think i have is: \
The predicted shape/coordinate is smaller. 
I think when the model are being trained, it reduced the values for better training which affected the result. 
![Screenshot 2025-03-03 at 1 01 04 AM](https://github.com/user-attachments/assets/b1081fef-9c06-4e55-9429-6ccad6729a8e)


