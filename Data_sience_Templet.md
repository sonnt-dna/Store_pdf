CHI TIẾT CÔNG VIỆC CẦN THỰC HIỆN TRONG QUÁ TRÌNH XÂY DỰNG VÀ TRIỂN KHAI DATA SIENCE WORKFLOW
Bước 	PMO	PO AND TEAM MEMBERS	Note công cụ
Bước 1	Sau khi PMO đã hỗ trợ nhóm tác giả tạo Workspace và phân quyền.
PMO hỗ trợ PO xin cấp phép truy cập và sử dụng tài nguyên (trang thiết bị (Capacity) và dữ liệu của Viện) theo đúng quy định của Viện.	PO và các thành viên nhóm xác định các nguồn tài liệu để phục nhiệm vụ  như đã được phê duyệt.	

Bước 2 (Bước 2A, 2B)
	Nhóm tác giả nhập dữ liệu từ bên ngoài, hoặc các nguồn trực tuyến có sẵn đã được cấp phép ở bước 1
	Có thể sử dụng DataFlow dữ liệu sẽ đi thẳng vào Lakehouse người dùng đã lựa chọn để lưu trữ.
	Các DA có thể sử dụng Notebook để xử lý dữ liệu thông qua công cụ Data Wrangle để xây dựng workflow xử lý dữ liệu.
	Người dùng thực hiện việc khai phá dữ liệu (EDA)
	1.Chuẩn hóa dữ liệu: Data Wrangler cho phép Người dùng thực hiện các hoạt động chuẩn hóa dữ liệu như xóa hàng và cột, lọc dữ liệu, đổi tên cột, đổi kiểu dữ liệu, và nhiều hơn nữa.
	2.Tự động nhận dạng kiểu dữ liệu: Công cụ này tự động nhận dạng kiểu dữ liệu của cột và đề xuất các hoạt động chuẩn hóa phù hợp.
	3.Xem trực quan: Người dùng có thể xem trước dữ liệu của mình thông qua biểu đồ và bảng để hiểu rõ hơn về các biến thể và quan hệ giữa chúng.
	4.Xử lý dữ liệu lớn: Data Wrangler được thiết kế để xử lý dữ liệu lớn, cho phép Người dùng làm việc với tập dữ liệu có kích thước lớn.

	Đồng thời toàn bộ các step tiến hành xử lý dữ liệu sẽ được xuất ra cell của notebook dưới dạng code, giúp người dùng hoàn toàn có thể lưu trữ và sử dụng cho các đối tượng DataFrame có cấu trúc data tương tự.

Lưu ý: Với bản preview trên Fabric thì hiện tại Data Wrangler chỉ hỗ trợ DataFrame Pandas, chưa hỗ trợ dạng Spark.

Link Miro hướng dẫn chi tiết: https://miro.com/app/board/uXjVMClAjPA=/
Bước 3 Người dùng có 2 cách lựa chọn để có thể xây dựng mô hình học máy
		Cách 1: Sử dụng AutoML của PowerBI services để xây dựng mô hình học máy, quy trình xây dựng mô hình học máy sử dụng AutoML được trình bày chi tiết và rõ ràng trong tài liệu sau từ trang 167 - 178.
		Cách 2: Dùng Notebook xây dựng mô hình học máy, người dùng có thể tham khảo mẫu quy trình Data sience, trong notebook mẫu có đầy đủ các bước thực hiện một dự án DataSicene (nhập liệu data, EDA, Feature Engineering, Train & Test và đo lường kết quả) với đường link sau:
	
Bước 4 Người dùng sử dụng AutoML để xây dựng mô hình học máy, các kết quả sẽ lưu lại trong report của mỗi lần chạy.
	Sau khi thực hiện quá trình xây dựng học máy người dùng cần lưu trữ các kết quả của các lần chạy thử nghiệm bằng việc sử dụng các các công cụ sẵn có trên nền tảng Fabric hoặc mã nguồn mở MLflow.
	Mỗi một project có thể tạo lập một hoặc nhiều Experiment khác nhau, chúng ta có thể lưu trữ nhiều lần chạy vào một Experiment.
		

Bước 5 và Bước 6 Xây dựng các Policy sử dụng Key Autho của các workspace và gửi cho DE:
	Những ai được cấp Key truy cập, thời gian sử dụng của mỗi Key,..
	Giới hạn lượng truy cập nếu có
	Key Auth sau khi đã cấu hình t theo các API mà DE cung cấp
	Dưới đây là 3 biểu mẫu cung cấp cách sử dụng ML (Experiment) trên các nền tảng lưu trữ (trên Fabric Notebook hoặc Machine learning sudio hoặc Dagshub):
	Hướng dẫn sử dụng Tracking trên nền tảng Fabric Notebook: LINK https://app.powerbi.com/links/vLFLKfVMf7?ctid=c5ec5abe-76c1-46cb-b3fe-c3b0071ffdb3&pbi_source=linkShare&experience=power-bi
	Hướng dẫn sử dụng Tracking trên Machine Learning Studio: LINK: https://app.powerbi.com/links/8J4qbYJG2f?ctid=c5ec5abe-76c1-46cb-b3fe-c3b0071ffdb3&pbi_source=linkShare&ctid=c5ec5abe-76c1-46cb-b3fe-c3b0071ffdb3&experience=data-science
	Hướng dẫn sử dụng Tracking trên Dagshub: LINK: https://app.powerbi.com/links/hkAG_iRBeh?ctid=c5ec5abe-76c1-46cb-b3fe-c3b0071ffdb3&pbi_source=linkShare&ctid=c5ec5abe-76c1-46cb-b3fe-c3b0071ffdb3&experience=data-science
	Người dùng hoàn toàn có thể lưu trữ trên Local
                 a. Hướng dẫn sử dụng Tracking trên máy tính local	
Bước 7
		Kết quả được lưu trên Machine Learning Studio
		Kết quả được lưu trên Dagshub
	
Bước 8	

	Kéo dữ liệu từ lakehouse để có thể visualization
Cung cấp SQL để có thể truy vấn được thông tin dữ liệu
	
Bước 9		Kết qủa có thể được hiển thị ở trên PowerBI report 
Có thể sử dụng SQL endpoint để truyền dữ liệu ra ngoài
Softcode truyền ra ngoài để tạo lập API
Chi tiết quy trình Link Miro: https://miro.com/app/board/uXjVMhAZW0s=/

#!/usr/bin/env python
# coding: utf-8

# ## Regression_ML_workflows
# # Regression ML workflow**
# # **I./ Khai báo thư viện**
# ## **1) Cài đặt thư viện**
# <mark>Nếu khi chạy khai báo thư viện mà cell hiện lỗi có dạng như: **ModuleNotFoundError: No module named 'tên-thư-viện'**: </mark>
# 
# **Chạy câu lệnh sau**:
# ```
# !pip install tên-thư-viện
# ```
get_ipython().system('pip install -q lightgbm==3.3.3')
get_ipython().system('pip install -q graphviz')
get_ipython().system('pip install -q bz2file==0.98')
get_ipython().system('pip install -q -U dataprep')
get_ipython().system('pip install -q Office365-REST-Python-Client')
get_ipython().system('pip install -q office365==0.3.15')
get_ipython().system('pip install -q dataprep==0.4.3')
get_ipython().system('pip install -q pycaret')
get_ipython().system('pip install -q catboost')
get_ipython().system('pip install -q optuna')


# ## **2) Khai báo thư viện**

# In[ ]:


'''
Các câu lệnh ở cell này để giúp notebook liên kết tới lakehouse muốn sử dụng
'''

import sys
sys.path.append('/lakehouse/default/Files')
sys.path.append('../')


# ### Python library

# Các thư viện Python là những **thư viện có sẵn** mà có thể sử dụng để thực hiện các tác vụ khác nhau như xử lý dữ liệu, đồ hoạ, học máy,...
# 
# Các thư viện này có thể tải xuống sử dụng câu lệnh
# ```
# pip install tên-thư-viện
# ```
# 
# Sau khi tải các thư viện xuống, người dùng có thể sử dụng bằng cách khai báo 
# ```
# import tên-thư-viện
# ```

# In[ ]:


# Public library
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import os, glob
import math
import pickle
import bz2file as bz2
import seaborn as sns
from datetime import datetime
import warnings
warnings.filterwarnings("ignore")


# In[ ]:


# # Import library from sklearn
from sklearn.model_selection import train_test_split, StratifiedShuffleSplit, GridSearchCV
from sklearn.compose import ColumnTransformer
from sklearn.pipeline import Pipeline
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.neighbors import KNeighborsClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.svm import SVC
from sklearn.naive_bayes import GaussianNB
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import StandardScaler, MinMaxScaler, LabelEncoder


# In[ ]:


# EDA Library
# import pandas_profiling as pp
from dataprep.eda import plot, plot_correlation, plot_missing, plot_diff, create_report
from dataprep.clean import clean_country, clean_df_gui


# In[ ]:


# Algorithm for machine learning
import lightgbm as lgb
import catboost as cat


# In[ ]:


#Conntor library with MLflow with Machine Learning Azure 
import azureml
from azureml.core import Workspace
import mlflow


# In[ ]:


# # Interactive Machine Learning 
from ipywidgets import interact, interactive, IntSlider, Layout, interact_manual
import ipywidgets as widgets
from IPython.display import display


# ### Custom library

# Custom library là một thư viện được **tạo ra bởi người dùng** hoặc tổ chức cụ thể để **đáp ứng nhu cầu cụ thể** của họ. 
# 
# Thư viện này chứa các hàm, lớp và công cụ được định nghĩa bởi người dùng để tái sử dụng trong các dự án Python của họ.

# In[ ]:


from CatBoost._catboostR import Train_CATR
from LightGBM._lightgbmR import Train_LGBMR
from LightGBM.score_cal import RScore
from XGBoost._xgboostR import Train_XGBR


# # **II./ Lấy dữ liệu**

# Việc nhập dữ liệu vào một cơ sở dữ liệu là một bước quan trọng trong việc quản lý và phân tích lượng thông tin lớn. Có một số cách để nhập dữ liệu vào cơ sở dữ liệu, bao gồm việc sử dụng một datamart, SharePoint hoặc một máy tính cá nhân.
# 
# - **SharePoint** là một <mark>nền tảng quản lý tài liệu và hợp tác dựa trên web</mark> có thể được sử dụng để lưu trữ và chia sẻ dữ liệu. Việc nhập dữ liệu vào SharePoint bao gồm tạo danh sách hoặc thư viện trong một trang SharePoint và sau đó sử dụng ứng dụng SharePoint Import Spreadsheet để tải lên dữ liệu từ một tệp Excel hoặc CSV.
# - **Datamart** là <mark>một phần nhỏ của một kho dữ liệu lớn hơn</mark> được thiết kế để phục vụ một nhóm cụ thể người dùng. Thường được tập trung vào một chức năng kinh doanh hoặc bộ phận cụ thể và cung cấp quyền truy cập nhanh chóng và dễ dàng vào dữ liệu liên quan. Việc nhập dữ liệu vào datamart bao gồm trích xuất dữ liệu từ các hệ thống nguồn, biến đổi nó thành định dạng phù hợp cho datamart và sau đó nạp nó vào datamart.
# - Việc nhập dữ liệu vào cơ sở dữ liệu local bao gồm cài đặt một hệ thống quản lý cơ sở dữ liệu (DBMS) trên máy tính cục bộ và sau đó sử dụng các công cụ đa dạng để nhập dữ liệu từ các nguồn khác nhau. Điều này có thể bao gồm việc sử dụng SQL Server Integration Services (SSIS) để trích xuất và biến đổi dữ liệu từ các nguồn khác nhau hoặc sử dụng một công cụ dòng lệnh như MySQLimport để nhập dữ liệu từ một tệp CSV.
# - <mark>**Tóm lại**</mark>, việc nhập dữ liệu vào cơ sở dữ liệu là <mark>một quy trình quan trọng cho phép tổ chức thu được thông tin từ dữ liệu của họ và đưa ra quyết định có cơ sở.</mark> Lựa chọn phương pháp sẽ phụ thuộc vào các yếu tố như lượng và phức tạp của dữ liệu, tài nguyên có sẵn và các yêu cầu cụ thể của tổ chức

# ### *Import data from Sharepoint.*

# In[ ]:


# site_url = 'https://viendaukhivn.sharepoint.com/sites/NVCVngdngAIdbomtvctnhntn'
# client_id= ''
# client_secret = ''

# client_credentials = ClientCredential(client_id,client_secret)
# ctx = ClientContext(site_url).with_credentials(client_credentials)

# file_url = ""
# download_path = '/work/20221711_Full_data_Goal_3_2.csv'
# #download_path = os.path.join(tempfile.mkdtemp(), os.path.basename(file_url))
# with open(download_path, "wb") as local_file:
#     file = ctx.web.get_file_by_server_relative_path(file_url).download(local_file).execute_query()
# print("[Ok] file has been downloaded into: {0}".format(download_path))

# with open(download_path, 'rb') as content_file:
#     file_content = content_file.read()
# # print(file_content)


# In[ ]:


# df = pd.read_excel(download_path)


# ### *Import data from local*

# In[ ]:


# Please input the link of data inside "...."
input_data = "/lakehouse/default/Files/Full_data_Goal_3_2.csv"


# In[ ]:


init_df = pd.read_csv(input_data)
df = init_df
display(df.info())
init_df.isnull().sum()
display(df.isnull().sum())
List_wells = init_df.WELL.unique()
feature_name = df.columns.tolist()


# # **III./ Quy trình xử lý**

# ### **1) Chọn các biến cần cho việc xử lý**

# Lựa chọn danh sách biến cho đầu vào là một bước quan trọng trong _**Feature Engineering**_, một quy trình lựa chọn và biến đổi dữ liệu thô thành các tính năng có thể được sử dụng để huấn luyện một mô hình học máy. 
# 
# Biến là một đặc điểm hoặc thuộc tính có thể đo lường của một điểm dữ liệu có thể được sử dụng để đưa ra dự đoán về dữ liệu mới, chưa được quan sát.
# - Để lựa chọn danh sách biến cho đầu vào, thường người ta bắt đầu bằng việc khám phá dữ liệu có sẵn để xác định các biến tiềm năng. Điều này có thể liên quan đến việc phân tích dữ liệu bằng cách sử dụng các kỹ thuật thống kê hoặc công cụ trực quan hóa dữ liệu để xác định các mẫu, xu hướng và mối quan hệ.
# - Sau khi các biến tiềm năng đã được xác định, chúng cần được biến đổi thành định dạng phù hợp để đưa vào mô hình học máy. Điều này có thể liên quan đến việc tỷ lệ, chuẩn hóa hoặc mã hóa dữ liệu để đảm bảo rằng nó là nhất quán và mang ý nghĩa.

# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_1:')

def on_variable_change(change):
    global Feature_1
    Feature_1 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_1: {Feature_1}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_2:')

def on_variable_change(change):
    global Feature_2
    Feature_2 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_2: {Feature_2}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_3:')

def on_variable_change(change):
    global Feature_3
    Feature_3 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_3: {Feature_3}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_4:')

def on_variable_change(change):
    global Feature_4
    Feature_4 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_4: {Feature_4}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_5:')

def on_variable_change(change):
    global Feature_5
    Feature_5 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_5: {Feature_5}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_6:')

def on_variable_change(change):
    global Feature_6
    Feature_6 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_6: {Feature_6}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_7:')

def on_variable_change(change):
    global Feature_7
    Feature_7 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_7: {Feature_7}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Feature_8:')

def on_variable_change(change):
    global Feature_8
    Feature_8 = change['new']
    # Perform actions based on the selected variable
    print(f'Feature_8: {Feature_8}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Outcome:')

def on_variable_change(change):
    global Outcome
    Outcome = change['new']
    # Perform actions based on the selected variable
    print(f'Outcome: {Outcome}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Category:')

def on_variable_change(change):
    global Category
    Category = change['new']
    # Perform actions based on the selected variable
    print(f'Category: {Category}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


_cols = [col for col in df if col not in ["Category", "DEPTH", Outcome]]
# processing pipeline
#Remove negative value   
def remove_negative_val(df, col):
    df_neg = df[df[col] < 0]
    df_neg[col] = np.nan
    df.loc[df_neg.index, col] = df_neg[col]
    return df
#Replace Null Value
def tweak_data(df):
    return (
        df
        .assign(
                Feature_1=df[Feature_1].replace({-9999.:np.nan}).astype('float64'),
                Feature_2=df[Feature_2].replace({-9999.:np.nan}).astype('float32'),
                Feature_3=df[Feature_3].replace({-9999.:np.nan}).astype('float32'),
                Feature_4=df[Feature_4].replace({-9999.:np.nan}).astype('float32'),
                Feature_5=df[Feature_5].replace({-9999.:np.nan}).astype('float32'),
                Feature_6=df[Feature_6].replace({-9999.:np.nan}).astype('float32'),
                Feature_7=df[Feature_7].replace({-9999.:np.nan}).astype('float32'),
                Feature_8=df[Feature_8].replace({-9999.:np.nan}).astype('float32')
                )
        .dropna(how="any", subset=[Outcome]).astype({"Feature_1": "int"})
        .pipe(remove_negative_val, Feature_1)
        .pipe(remove_negative_val, Feature_2)
        .pipe(remove_negative_val, Feature_3)
        .pipe(remove_negative_val, Feature_4)
        .pipe(remove_negative_val, Feature_5)
        .pipe(remove_negative_val, Feature_6)
        .pipe(remove_negative_val, Feature_7)
        .pipe(remove_negative_val, Feature_8)
    )


# ## **2) Xử lý dữ liệu**

# ### 2.1. Feature Engineering

# **Feature Engineering** là quá trình xử lý dữ liệu để **tạo ra các đặc trưng mới** hoặc **cải thiện các đặc trưng hiện có** để cải thiện hiệu quả của mô hình dự đoán. 
# 
# Sau đây là các bước chính trong quá trình Feature Engineering:

# - <mark>Xem xét dữ liệu</mark>: Trước khi bắt đầu tạo các đặc trưng mới, bạn cần hiểu rõ về dữ liệu đang có và cách nó được tổ chức.

# - <mark>Tạo các đặc trưng mới</mark>: Dựa trên sự hiểu biết về dữ liệu, bạn có thể tạo ra các đặc trưng mới dựa trên các đặc trưng hiện có. Các đặc trưng mới này có thể là sự kết hợp của các đặc trưng hiện có hoặc các đặc trưng được tạo ra từ phân tích đồ thị hoặc bài toán liên quan.

# - <mark>Chuẩn hóa dữ liệu</mark>: Khi sử dụng các mô hình dự đoán, quy tắc đặc trưng chung là các đặc trưng nên được chuẩn hóa. Chuẩn hóa có thể giúp cho mô hình hội tụ nhanh hơn và dễ dàng hơn khi đặc trưng có phạm vi giá trị lớn hơn.

# - <mark>Lựa chọn đặc trưng</mark>: Trong trường hợp có nhiều đặc trưng, bạn cần chọn ra những đặc trưng quan trọng nhất để giảm chi phí tính toán và tăng độ chính xác của mô hình. Bạn có thể sử dụng các kỹ thuật như L1 regularization, đường cong ROC hoặc phương pháp nhúng để tìm ra các đặc trưng quan trọng.

# In[ ]:


# execute above code
df = tweak_data(df)
df = df.replace({-9999: np.nan}).dropna(how='any', subset=[Outcome])
new_list_feature = [Feature_1, Feature_2, Feature_3, Feature_4, Feature_5, Feature_6, Feature_7, Feature_8]
label_name = Outcome


# Check Data after Feature Engineering

# ### Quickview data

# In[ ]:


#After droping nan values
# Basic statistical check including additional 1, 5 and 95, 99 percentiles - training well: w1
display(df[feature_name].describe(percentiles=[0.01,0.05,0.25,0.5,0.75,0.95,0.99]))
# display(df.info())


# In[ ]:


# Người dùng có thể thay đổi Category để phân loại 
for well in df[Category].unique():
    print(well)
    df_well = df[df[Category] == well]
    fig,axes = plt.subplots(nrows=2, ncols=3,figsize=(17,8))
    axes = axes.flatten()
    ax1 = axes[0]
    ax1.scatter(df_well[Feature_1], df_well[Outcome])
    ax1.set_xlabel(Feature_1)
    ax1.set_ylabel(Outcome)
    ax2 = axes[1]
    ax2.scatter(df_well[Feature_2], df_well[Outcome])
    ax2.set_xlabel(Feature_2)
    ax2.set_ylabel(Outcome)
    ax3 = axes[2]
    ax3.scatter(df_well[Feature_3], df_well[Outcome])
    ax3.set_xlabel(Feature_3)
    ax3.set_ylabel(Outcome)
    ax4 = axes[3]
    ax4.scatter(df_well[Feature_4], df_well[Outcome])
    ax4.set_xlabel(Feature_4)
    ax4.set_ylabel(Outcome)
    ax5 = axes[4]
    ax5.scatter(df_well[Feature_5], df_well[Outcome])
    ax5.set_xlabel(Feature_5)
    ax5.set_ylabel(Outcome)
    ax6 = axes[5]
    ax6.scatter(df_well[Feature_5], df_well[Outcome])
    ax6.set_xlabel(Feature_5)
    ax6.set_xscale('log')
    ax6.set_ylabel(Outcome)
    plt.show()


# 2.2. Principal Component Analysis (PCA)

# PCA Papper

# https://oaktrust.library.tamu.edu/bitstream/handle/1969.1/169590/ZHOU-THESIS-2017.pdf?sequence=1&isAllowed=yhttps://scheevel.com/pdf_files/SPE_56734_Scheevel_Payrazyan.pdf

# In[ ]:


# Step 1: Importing the libraries 
# importing required libraries

# Discretization using cut method of pandas package
cut_labels = ["1", "2", "3", "4"]
cut_bins = [0, 1, 1.5, 2, 2.5]#0: min, 25: max
df["Cat"] = pd.cut(df[Outcome].astype('float32'), bins = cut_bins, labels = cut_labels)
# importing or loading the dataset
dataset = df
dataset = dataset.dropna()
label_name = ["Cat"]
# Step 2: Importing the data set
# Import the dataset and distributing the dataset into X and y components for data analysis.
# distributing the dataset into two components X and Y
feature_names_PCA = [col for col in df.columns if col not in [Category,Feature_1,Outcome, "index"
                                                       
                                                          ]]
X = dataset[feature_names_PCA]
y = dataset["Cat"]

# Step 3: Splitting the dataset into the Training set and Test set
# Splitting the X and Y into the
# Training set and Testing set

df_PCA = df.replace([np.inf, -np.inf], np.nan)
df_PCA = df_PCA.dropna()
df_PCA = df_PCA.reset_index()

## split data
### some data for test model after deploy
ss = StratifiedShuffleSplit(n_splits=1, test_size=0.2, random_state=42)

for _train_inx, _test_inx in ss.split(df_PCA, df_PCA["WELL"]):
    train_df_PCA, test_df_PCA = df_PCA.loc[_train_inx, :], df_PCA.loc[_test_inx, :]
X_train_PCA, X_test_PCA, y_train_PCA, y_test_PCA = train_test_split(
    train_df_PCA[feature_names_PCA],
    train_df_PCA[label_name],
    train_size=0.9,
    random_state=42,
)
# performing preprocessing part

sc = StandardScaler()

# Step 4: Feature Scaling
# Doing the pre-processing part on training and testing set such as fitting the Standard scale.
# X_train_PCA = X_train_PCA.dropna()
# X_test_PCA = X_test_PCA.dropna()


X_train_PCA = sc.fit_transform(X_train_PCA)
# X_test_DCA = pd.DataFrame(StandardScaler().fit_transform(X_test), columns=X_test.columns, index=X_test.index)
X_train_PCA = sc.transform(X_train_PCA)

# Step 5: Applying PCA function
# Applying the PCA function into the training and testing set for analysis. 
# and testing set of X component
from sklearn.decomposition import PCA

pca = PCA(n_components = 2)

X_train_PCA = pca.fit_transform(X_train_PCA)
X_test_PCA = pca.transform(X_test_PCA)
pca.fit(X_train_PCA)
explained_var_ratio = pca.explained_variance_ / np.sum(pca.explained_variance_)

# Step 6: Fitting Logistic Regression To the training set
# Fitting Logistic Regression To the training set
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier, RandomTreesEmbedding, ExtraTreesClassifier

#Select calssifier for model
# classifier = LogisticRegression(random_state = 42)
classifier = RandomForestClassifier(random_state = 42)
# classifier = ExtraTreesClassifier(max_depth=3, n_estimators=10, random_state=0)

classifier.fit(X_train_PCA, y_train_PCA)

# Step 7: Predicting the test set result 
# Predicting the test set result using
# predict function under LogisticRegression
y_pred = classifier.predict(X_test_PCA)

# Step 8: Making the confusion matrix 
# making confusion matrix between
# test set of Y and predicted value.
from sklearn.metrics import confusion_matrix
cm = confusion_matrix(y_test_PCA, y_pred)

# Step 9: Predicting the training set result
# Predicting the training set
# result through scatter plot
from matplotlib.colors import ListedColormap

X_set, y_set = X_train_PCA, y_train_PCA
X1, X2 = np.meshgrid(np.arange(start = X_set[:, 0].min() - 1,
					stop = X_set[:, 0].max() + 1, step = 0.01),
					np.arange(start = X_set[:, 1].min() - 1,
					stop = X_set[:, 1].max() + 1, step = 0.01))

plt.contourf(X1, X2, classifier.predict(np.array([X1.ravel(),
			X2.ravel()]).T).reshape(X1.shape), alpha = 0.75,
			cmap = ListedColormap(('yellow', 'lime', 'aquamarine', "brown")))

plt.xlim(X1.min(), X1.max())
plt.ylim(X2.min(), X2.max())

for i, j in enumerate(np.unique(y_set)):
	plt.scatter(X_set[y_set == j, 0], X_set[y_set == j, 1],
				c = ListedColormap(('red', 'green', 'blue', "brown"))(i), label = j)

plt.title('Logistic Regression (Training set)')
plt.xlabel('PC1') # for Xlabel
plt.ylabel('PC2') # for Ylabel
plt.legend() # to show legend

# show scatter plot
plt.show()


# # DataPrep

# ### Create Overview

# In[ ]:


plot(df[new_list_feature])


# ### Understand Missing Values

# #### 1. Missing value overview

# In[ ]:


plot_missing(df[new_list_feature])


# In[ ]:


df[new_list_feature]


# #### 2. Impact of missing value

# In[ ]:


df


# In[ ]:


# Understand how the distribution of other columns change
# After droping the missing values of 'GR' column.
# plot_missing(init_df2, 'Fracture zone')
df_mis = df[new_list_feature].fillna('')
plot_missing(df_mis, Feature_2)


# ### Understand correlation

# #### 1. Correlation overview

# In[ ]:


plot_correlation(df[new_list_feature])


# #### 2. Understand how other columns correlated to the given column

# In[ ]:


# columns are sorted by their correlation to selected column.
plot_correlation(df[new_list_feature], Feature_3)


# ### Understand single column

# #### 1. Numerical column

# In[27]:


for well in df.WELL.unique():
    print (well)
    plot(df[df["WELL"] == well], Outcome)


# #### 2. Categorical column

# In[ ]:


plot(df, Outcome)


# ### Understand column relationship

# #### 1. Numerical vs Numerical

# In[28]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X:')

def on_variable_change(change):
    global X
    X = change['new']
    # Perform actions based on the selected variable
    print(f'X: {X}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[29]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Y:')

def on_variable_change(change):
    global Y
    Y = change['new']
    # Perform actions based on the selected variable
    print(f'Y: {Y}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


plot(df,X, Y)


# In[ ]:


plot(df,X, Y)


# #### 2. Numerical vs Categorical

# In[30]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X:')

def on_variable_change(change):
    global X
    X = change['new']
    # Perform actions based on the selected variable
    print(f'X: {X}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[31]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X_2:')

def on_variable_change(change):
    global X_2
    X_2 = change['new']
    # Perform actions based on the selected variable
    print(f'X_2: {X_2}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[32]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X_3:')

def on_variable_change(change):
    global X_3
    X_3 = change['new']
    # Perform actions based on the selected variable
    print(f'X_3: {X_3}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[33]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X_4:')

def on_variable_change(change):
    global X_4
    X_4 = change['new']
    # Perform actions based on the selected variable
    print(f'X_4: {X_4}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[34]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X_5:')

def on_variable_change(change):
    global X_5
    X_5 = change['new']
    # Perform actions based on the selected variable
    print(f'X_5: {X_5}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[35]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X_6:')

def on_variable_change(change):
    global X_6
    X_6 = change['new']
    # Perform actions based on the selected variable
    print(f'X_6: {X_6}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[36]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X_7:')

def on_variable_change(change):
    global X_7
    X_7 = change['new']
    # Perform actions based on the selected variable
    print(f'X_7: {X_7}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[37]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X_8:')

def on_variable_change(change):
    global X_8
    X_8 = change['new']
    # Perform actions based on the selected variable
    print(f'X_8: {X_8}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


import plotly.express as px
import numpy as np

# Generate data
x = df[X]
y = df[X_2]
z = df[X_3]
c= df[X_4]

fig = px.scatter_3d(df, x=x, y=y, z=z, color=c, hover_data=[X_5, X_6,X_7])
# fig.update_layout(scene_zaxis_type="log")
fig.update_layout(height=600, width=800,
                  title='3D views')


# List of color bar

# Accent’, ‘Accent_r’, ‘Blues’, ‘Blues_r’, ‘BrBG’, ‘BrBG_r’, ‘BuGn’, ‘BuGn_r’, ‘BuPu’, ‘BuPu_r’, ‘CMRmap’, ‘CMRmap_r’, ‘Dark2’, ‘Dark2_r’, ‘GnBu’, ‘GnBu_r’,  ‘Greens’, ‘Greens_r’, ‘Greys’, ‘Greys_r’, ‘OrRd’, ‘OrRd_r’, ‘Oranges’, ‘Oranges_r’,  ‘PRGn’, ‘PRGn_r’, ‘Paired’, ‘Paired_r’, ‘Pastel1’, ‘Pastel1_r’, ‘Pastel2’,  ‘Pastel2_r’, ‘PiYG’, ‘PiYG_r’, ‘PuBu’, ‘PuBuGn’, ‘PuBuGn_r’, ‘PuBu_r’, ‘PuOr’, ‘PuOr_r’, ‘PuRd’, ‘PuRd_r’, ‘Purples’, ‘Purples_r’, ‘RdBu’, ‘RdBu_r’, ‘RdGy’, ‘RdGy_r’, ‘RdPu’, ‘RdPu_r’, ‘RdYlBu’, ‘RdYlBu_r’, ‘RdYlGn’, ‘RdYlGn_r’, ‘Reds’, ‘Reds_r’, ‘Set1’, ‘Set1_r’, ‘Set2’, ‘Set2_r’, ‘Set3’, ‘Set3_r’, ‘Spectral’, ‘Spectral_r’, ‘Wistia’, ‘Wistia_r’, ‘YlGn’, ‘YlGnBu’, ‘YlGnBu_r’, ‘YlGn_r’, ‘YlOrBr’, ‘YlOrBr_r’, ‘YlOrRd’, ‘YlOrRd_r’, ‘afmhot’, ‘afmhot_r’, ‘autumn’, ‘autumn_r’, ‘binary’, ‘binary_r’,  ‘bone’, ‘bone_r’, ‘brg’, ‘brg_r’, ‘bwr’, ‘bwr_r’, ‘cividis’, ‘cividis_r’, ‘cool’, ‘cool_r’,  ‘coolwarm’, ‘coolwarm_r’, ‘copper’, ‘copper_r’, ‘cubehelix’, ‘cubehelix_r’, ‘flag’, ‘flag_r’,  ‘gist_earth’, ‘gist_earth_r’, ‘gist_gray’, ‘gist_gray_r’, ‘gist_heat’, ‘gist_heat_r’, ‘gist_ncar’,  ‘gist_ncar_r’, ‘gist_rainbow’, ‘gist_rainbow_r’, ‘gist_stern’, ‘gist_stern_r’, ‘gist_yarg’,  ‘gist_yarg_r’, ‘gnuplot’, ‘gnuplot2’, ‘gnuplot2_r’, ‘gnuplot_r’, ‘gray’, ‘gray_r’, ‘hot’, ‘hot_r’,  ‘hsv’, ‘hsv_r’, ‘icefire’, ‘icefire_r’, ‘inferno’, ‘inferno_r’, ‘jet’, ‘jet_r’, ‘magma’, ‘magma_r’,  ‘mako’, ‘mako_r’, ‘nipy_spectral’, ‘nipy_spectral_r’, ‘ocean’, ‘ocean_r’, ‘pink’, ‘pink_r’,  ‘plasma’, ‘plasma_r’, ‘prism’, ‘prism_r’, ‘rainbow’, ‘rainbow_r’, ‘rocket’, ‘rocket_r’,  ‘seismic’, ‘seismic_r’, ‘spring’, ‘spring_r’, ‘summer’, ‘summer_r’, ‘tab10’, ‘tab10_r’,’tab20′, ‘tab20_r’, ‘tab20b’, ‘tab20b_r’, ‘tab20c’, ‘tab20c_r’, ‘terrain’, ‘terrain_r’, ‘turbo’,  ‘turbo_r’, ‘twilight’, ‘twilight_r’, ‘twilight_shifted’, ‘twilight_shifted_r’, ‘viridis’,  ‘viridis_r’, ‘vlag’, ‘vlag_r’, ‘winter’, ‘winter_r’

# #### 3. Categorical vs Categorical

# In[38]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X:')

def on_variable_change(change):
    global X
    X = change['new']
    # Perform actions based on the selected variable
    print(f'X: {X}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[39]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select Y:')

def on_variable_change(change):
    global Y
    Y = change['new']
    # Perform actions based on the selected variable
    print(f'Y: {Y}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


plot(df, X, Y)


# ### Customize Visualization

# #### 1. Show only interested visualizations

# In[26]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X:')

def on_variable_change(change):
    global X
    X = change['new']
    # Perform actions based on the selected variable
    print(f'X: {X}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


plot(df,X)


# #### 2. Set config for visualization

# In[ ]:


variable_names = ['','DEPTH', 'WELL', 'GR', 'Fracture Intensity', 'LLD', 'LLS', 'DCALI_FINAL', 'NPHI','RHOB', 'DTC', 'DTS']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select X:')

def on_variable_change(change):
    global X
    X = change['new']
    # Perform actions based on the selected variable
    print(f'X: {X}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[ ]:


# Set height and bins for the histogram
plot(df, X, display= ['Histogram'], config = {'hist.bins': 100, 'hist.yscale': 'linear', 'hist.color': '#aec7e8', 'height': 600, 'width': 400})


# # Modeling

# ## Define training/testing data

# In[27]:


feature_names = [col for col in df.columns if col not in [Category, "DEPTH", Outcome, 
                                                        #    "index",
                                                          ]]
# df = df[df[label_name] >= 0]
# df = df.reset_index()
## split data
### some data for test model after deploy
ss = StratifiedShuffleSplit(n_splits=1, test_size=0.2, random_state=42)
# for _train_inx, _test_inx in ss.split(df, df[label_name]):
for _train_inx, _test_inx in ss.split(df, df[Category]):
    train_df, test_df = df.loc[_train_inx, :], df.loc[_test_inx, :]

X_train, X_test, y_train, y_test = train_test_split(
    train_df[feature_names],
    train_df[label_name],
    # stratify=train_df[label_name],
    train_size=0.9,
    random_state=42,
)

### create lgb dataset
train_set = lgb.Dataset(
    X_train,
    label=y_train,
    feature_name=feature_names,
)
valid_set = lgb.Dataset(
    X_test,
    label=y_test,
    reference=train_set,
    feature_name=feature_names,
)


# ## Custom metric

# In[28]:


from sklearn.metrics import recall_score, precision_score, accuracy_score, f1_score, roc_auc_score, precision_recall_curve
def _my_metric(preds, data, threshold:float=0.5):
    """An eval metric that always returns the same value"""
    metric_name = 'my_metric'
    y_preds = preds >= threshold
    value = recall_score(data.get_label(), y_preds)
    is_higher_better = True
    return metric_name, value, is_higher_better


# ## Training

# In[29]:


variable_names = ['','gamma','MAE', 'RMSE', 'R2']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select scoring:')

def on_variable_change(change):
    global scoring
    scoring = change['new']
    # Perform actions based on the selected variable
    print(f'scoring: {scoring}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[30]:


variable_names = ['','valid_score', 'train_valid_drop']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select objective:')

def on_variable_change(change):
    global objective
    objective = change['new']
    # Perform actions based on the selected variable
    print(f'objective: {objective}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[31]:


variable_names = ['','catboost', 'xgboost', 'lightgbm', 'RandomForest', 'ExtraTree', 'KNN', 'Linear_Regression']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select algorithm:')

def on_variable_change(change):
    global algorithm
    algorithm = change['new']
    # Perform actions based on the selected variable
    print(f'algorithm: {algorithm}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[32]:


variable_names = ['','True', 'False']

dropdown = widgets.Dropdown(options=variable_names, description= f'Select show_shap:')

def on_variable_change(change):
    global show_shap
    show_shap = change['new']
    # Perform actions based on the selected variable
    print(f'show_shap: {show_shap}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# In[33]:


dropdown = widgets.IntText(description= f'Enter iteration:')

def on_variable_change(change):
    global iteration
    iteration = change['new']
    # Perform actions based on the selected variable
    print(f'iteration: {iteration}')

dropdown.observe(on_variable_change, names='value')

display(dropdown)


# ##Starting for Training

# In[40]:


# data = df[new_list_feature]
from sklearn.preprocessing import FunctionTransformer
from sklearn.model_selection import GridSearchCV
import joblib

def custom_encoder(data):
    le = LabelEncoder()
    for col in data.loc[: , data.dtypes == np.object].columns:
        data[col] = le.fit_transform(data[col].astypeastype(str))
    return data
seed = 42
data = df
target = Outcome

# drop = feature.copy()
# drop.append(target)
# drop
data = data.dropna(how ='any')
if objective == 'valid_score':
    objective = 0
else:
    objective = 1
if target==0:
    if algorithm == 'xgboost':
        task = 'reg:gamma'
    elif algorithm == 'lightgbm':
        task = 'gamma'
    elif algorithm == 'RandomForest':
        task = 'gamma'
    elif algorithm == 'ExtraTree':
        task = 'gamma'
    elif algorithm == 'Regression':
        task = 'gamma'
    elif algorithm == 'KNN':
        task = 'gamma'
    else:
        task ='MAE'
else:
    if algorithm == 'xgboost':
        task = 'reg:squarederror'
    elif algorithm == 'lightgbm':
        task = 'regression'
    else:
        task = 'RMSE'

y=data[target]
X=data[new_list_feature]
# print(X)
#split data into sets
X_use, X_test, y_use, y_test = train_test_split(X, y, train_size=0.9, random_state=seed, shuffle=True)
X_train, X_valid, y_train, y_valid = train_test_split(X_use, y_use, train_size=0.8, random_state=seed, shuffle=True)
preprocessors = Pipeline(steps=
        [
            ("imputer", SimpleImputer(strategy='most_frequent')),
            ("scaling", MinMaxScaler())
    ]
)
#print(X_train.shape)
X_train, X_valid = preprocessors.fit_transform(X_train), preprocessors.transform(X_valid)
X_test = preprocessors.transform(X_test)
timestamp = datetime.now().strftime("%Y-%m-%d-%H")
scaler_save = '/lakehouse/default/Files/scaler_'+algorithm+'_'+ target+ '_'+well+'_'+timestamp+'.pkl'
# joblib.dump(preprocessors,scaler_save)

#print(feature)
X_train = pd.DataFrame(X_train, columns=new_list_feature)
X_valid = pd.DataFrame(X_valid, columns=new_list_feature)
X_test  = pd.DataFrame(X_test, columns=new_list_feature)
print(X_train)


# In[ ]:


if algorithm=='lightgbm':
    model = lgb.train(
    params={
        "boosting_type": "gbdt",
        "objective": "poisson",
        "metric": "poisson",
        # "is_unbalance": True,
        "learning_rate": 0.05,
        "random_state": 42,
        "max_bin": 256,
        "max_depth": 20,
        "num_leaves": 128,

    },
    # params=params,
    train_set=lgb.Dataset(data=X_train, label=y_train,
                          feature_name=new_list_feature),
    num_boost_round=5000,
    valid_sets=lgb.Dataset(data=X_test, label=y_test,
                           feature_name=new_list_feature),
    early_stopping_rounds=5,
    # verbose_eval=0,  callbacks=[_callbacks],
)
    model.save_model(filename='/lakehouse/default/Files/Model_Goal.json')
    model = Train_LGBMR(
        features = X_train,
        target = y_train,
        iterations = int(iteration),
        scoring = scoring,
        validation_set = (X_valid, y_valid),
        test_set= (X_test, y_test),
        task = task,
        base_score=0.75,
        objectives = objective,
        show_shap = show_shap,
        refit=False,
        saved_dir='lightgbm_shaps'
        )
    y_pred = model.predict(X_test)
    score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)
    print("Testing ScoreScore:", score)

elif algorithm =='xgboost':
    model = Train_XGBR(
        features = X_train,
        target = y_train,
        iterations = int(iteration),
        scoring = scoring,
        validation_set = (X_valid, y_valid),
        base_score=0.75,
        test_set= (X_test, y_test),
        task = task,
        objectives = objective,
        show_shap = show_shap,
        refit = False,
        saved_dir='xgboost_shaps'
        )
    y_pred=model.predict(xgb.DMatrix(data=X_test, label=y_test))
    score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)
    print(f"Test score: {score}")

elif algorithm =='RandomForest':
    from sklearn.model_selection import GridSearchCV
    from sklearn.pipeline import Pipeline
    from sklearn.preprocessing import StandardScaler
    from sklearn.ensemble import RandomForestRegressor

    # define a wrapper class for GridSearchCV
    class GridSearchCVWrapper:
        def __init__(self, model):
            self.model = model
        
        def fit(self, X_train, y_train, param_grid, cv=5, n_jobs=-1, verbose=2, error_score='raise', max_iter=1):
            # create pipeline
            pipe = Pipeline([
                ('scaler', StandardScaler()),
                ('clf', self.model)
            ])
            
            # perform grid search
            grid_search = GridSearchCV(pipe, param_grid=param_grid, cv=cv, n_jobs=n_jobs, verbose=verbose, error_score=error_score)
            grid_search.fit(X_train, y_train)
            
            # set best parameters for the model
            best_params= {k.replace('clf__', ''): v for k, v in grid_search.best_params_.items()}
            self.model.set_params(**best_params)
            # return best parameters and score
            return grid_search.best_params_, grid_search.best_score_

    # define parameter grid for RandomForestRegressor
    parameters = {
        'clf__n_estimators': [50, 100, 200],
        'clf__max_features': ['auto', 'sqrt', 'log2'],
        'clf__max_depth' : [10, 20, 30, None],
        'clf__min_samples_split': [2, 5, 10],
        'clf__min_samples_leaf': [1, 2, 4],
    }

    # perform grid search for RandomForestRegressor
    model = GridSearchCVWrapper(RandomForestRegressor())
    rf_best_params, rf_best_score = model.fit(X_train, y_train, parameters)

    print("RandomForestRegressor:")
    print("Best Parameters:", rf_best_params)
    print("Best Score:", rf_best_score)

    # Evaluate the model's performance
    model = Pipeline([
        ('scaler', StandardScaler()),
        ('clf', RandomForestRegressor(**{k.replace('clf__', ''): v for k, v in rf_best_params.items()}))
    ])

    # fit pipeline to entire dataset
    model.fit(X_train, y_train)

    # predict on new data
    y_pred = model.predict(X_test)  
    score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)


    print(f"Test score: {score}")
elif algorithm =='ExtraTree':
    from sklearn.datasets import load_iris
    from sklearn.model_selection import GridSearchCV
    from sklearn.pipeline import Pipeline
    from sklearn.preprocessing import StandardScaler
    from sklearn.ensemble import ExtraTreesRegressor
    from sklearn.tree import ExtraTreesRegressor

    # define a wrapper class for GridSearchCV
    class GridSearchCVWrapper:
        def __init__(self, model):
            self.model = model
        
        def fit(self, X_train, y_train, param_grid, cv=5, n_jobs=-1, verbose=2, error_score='raise'):
            # create pipeline
            pipe = Pipeline([
                ('scaler', StandardScaler()),
                ('clf', self.model)
            ])
            
            # perform grid search
            grid_search = GridSearchCV(pipe, param_grid=param_grid, cv=cv, n_jobs=n_jobs, verbose=verbose, error_score=error_score)
            grid_search.fit(X_train, y_train)
            
            # return best parameters and score
            return grid_search.best_params_, grid_search.best_score_

    # define parameter grid for ExtraTreeClassifier
    parameters = {
        'clf__criterion': ['gini', 'entropy'],
        'clf__splitter': ['best', 'random'],
        'clf__max_depth': [3, 5, 7, 9],
        'clf__min_samples_split': [2, 5, 10],
        'clf__min_samples_leaf': [1, 2, 4],
        'clf__max_features': ['sqrt', 'log2', None],
    }

    # perform grid search for ExtraTreesRegressor
    model = GridSearchCVWrapper(ExtraTreesRegressor())
    extratree_best_params, extratree_best_score = model.fit(X_train, y_train, parameters)

    # Evaluate the model's performance
    model = Pipeline([
        ('scaler', StandardScaler()),
        ('clf', ExtraTreesRegressor(**{k.replace('clf__', ''): v for k, v in extratree_best_params.items()}))
    ])

    # fit pipeline to entire dataset
    model.fit(X_train, y_train)

    # predict on new data
    y_pred = model.predict(X_test)  
    score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)
    
    # print best parameters and score for ExtraTreeClassifier
    print("ExtraTreeClassifier:")
    print("Best Parameters:", extratree_best_params)
    print("Best Score:", extratree_best_score)
    print(f"Test score: {score}")

elif algorithm =='Linear_Regression':
    # # create pipeline with label encoder and LinearRegression
    from sklearn.linear_model import LinearRegression

    # define a wrapper class for GridSearchCV
    class GridSearchCVWrapper:
        def __init__(self, model):
            self.model = model
        
        def fit(self, X_train, y_train, param_grid, cv=5, n_jobs=-1, verbose=2, error_score='raise', max_iter=1):
            # create pipeline
            pipe = Pipeline([
                ('scaler', StandardScaler()),
                ('clf', self.model)
            ])
            
            # perform grid search
            grid_search = GridSearchCV(pipe, param_grid=param_grid, cv=cv, n_jobs=n_jobs, verbose=verbose, error_score=error_score)
            grid_search.fit(X_train, y_train)
            
            # set best parameters for the model
            best_params= {k.replace('clf__', ''): v for k, v in grid_search.best_params_.items()}
            self.model.set_params(**best_params)
            # return best parameters and score
            return grid_search.best_params_, grid_search.best_score_

    # define parameter grid for LinearRegression
    linear_params = {
        'clf__fit_intercept': [True, False],
    }

    # perform grid search for LinearRegression
    model = GridSearchCVWrapper(LinearRegression())
    linear_best_params, linear_best_score = model.fit(X_train, y_train, linear_params)

    # print best parameters and score for LinearRegression
    print("LinearRegression:")
    print("Best Parameters:", linear_best_params)
    print("Best Score:", linear_best_score)

    # train model with best parameters on full dataset
    model = Pipeline([
        ('scaler', StandardScaler()),
        ('clf', LinearRegression(**{k.replace('clf__', ''): v for k, v in linear_best_params.items()}))
    ])

    model.fit(X_train, y_train)

    # Evaluate the model's performance
    y_pred = model.predict(X_test)   
    score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)
    print(f"Test score: {score}")

#K-Nearest Neighbors (KNN)
elif algorithm =='KNN':
    from sklearn.neighbors import KNeighborsRegressor
    from sklearn.preprocessing import LabelEncoder

    # define a wrapper class for GridSearchCV
    class GridSearchCVWrapper:
        def __init__(self, model):
            self.model = model
        
        def fit(self, X_train, y_train, param_grid, cv=5, n_jobs=-1, verbose=2, error_score='raise'):
            # create pipeline
            pipe = Pipeline([
                ('scaler', StandardScaler()),
                ('clf', self.model)
            ])
            
            # perform grid search
            grid_search = GridSearchCV(pipe, param_grid=param_grid, cv=cv, n_jobs=n_jobs, verbose=verbose, error_score=error_score)
            grid_search.fit(X_train, y_train)
            
            # return best parameters and score
            return grid_search.best_params_, grid_search.best_score_

    # define parameter grid for KNeighborsRegressor
    knn_params = {
        'clf__n_neighbors': [3, 5, 7, 9],
        'clf__weights': ['uniform', 'distance'],
        'clf__algorithm': ['auto', 'ball_tree', 'kd_tree', 'brute'],
        'clf__leaf_size': [10, 20, 30, 40, 50],
        'clf__p': [1, 2],
    }

    # perform grid search for KNeighborsRegressor
    model = GridSearchCVWrapper(KNeighborsRegressor())
    knn_best_params, knn_best_score = model.fit(X_train, y_train, knn_params)

    # print best parameters and score for KNeighborsRegressor
    print("KNeighborsRegressor:")
    print("Best Parameters:", knn_best_params)
    print("Best Score:", knn_best_score)

    # train model with best parameters on full dataset
    model = Pipeline([
        ('scaler', StandardScaler()),
        ('clf', KNeighborsRegressor(**{k.replace('clf__', ''): v for k, v in knn_best_params.items()}))
    ])
    model.fit(X_train, y_train)

    # Evaluate the model's performance
    y_pred = model.predict(X_test)   
    score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)
    print(f"Test score: {score}")
else:
    model= Train_CATR(
        features=X_train,
        target=y_train,
        iterations = int(iteration), 
        base_score=0.75,
        scoring=scoring,
        validation_set = (X_valid, y_valid),
        test_set=(X_test, y_test),
        task=task,
        objectives=objective, #{0: "valid_score", 1: "train_valid_drop"}
        show_shap=show_shap, # flag to show shap True or False
        refit=False,
        )
    y_pred=model.predict(cat.Pool(data=X_test, label=y_test))
    score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)
    print(f"Test score: {score}")
model_save = '/lakehouse/default/Files/model_'+algorithm+'_'+ target+'_'+timestamp+'.pkl'
joblib.dump(model,model_save)
print(scaler_save)
print(model_save)


# LogisticRegression

# In[ ]:


# from sklearn.model_selection import GridSearchCV
# from sklearn.pipeline import Pipeline
# from sklearn.preprocessing import StandardScaler
# from sklearn.linear_model import LinearRegression
# from sklearn.metrics import mean_squared_error, r2_score

# # define a wrapper class for GridSearchCV
# class GridSearchCVWrapper:
#     def __init__(self, model):
#         self.model = model
    
#     def fit(self, X_train, y_train, param_grid, cv=5, n_jobs=-1, verbose=2, error_score='raise', max_iter=1):
#         # create pipeline
#         pipe = Pipeline([
#             ('scaler', StandardScaler()),
#             ('clf', self.model)
#         ])
        
#         # perform grid search
#         grid_search = GridSearchCV(pipe, param_grid=param_grid, cv=cv, n_jobs=n_jobs, verbose=verbose, error_score=error_score)
#         grid_search.fit(X_train, y_train)
        
#         # set best parameters for the model
#         best_params= {k.replace('clf__', ''): v for k, v in grid_search.best_params_.items()}
#         self.model.set_params(**best_params)
#         # return best parameters and score
#         return grid_search.best_params_, grid_search.best_score_

# # define parameter grid for LinearRegression
# linear_params = {
#     'clf__fit_intercept': [True, False],
# }

# # perform grid search for LinearRegression
# linear_wrapper = GridSearchCVWrapper(LinearRegression())
# linear_best_params, linear_best_score = linear_wrapper.fit(X_train, y_train, linear_params)

# # print best parameters and score for LinearRegression
# print("LinearRegression:")
# print("Best Parameters:", linear_best_params)
# print("Best Score:", linear_best_score)

# # train model with best parameters on full dataset
# pipe = Pipeline([
#     ('scaler', StandardScaler()),
#     ('clf', LinearRegression(**{k.replace('clf__', ''): v for k, v in linear_best_params.items()}))
# ])

# pipe.fit(X_train, y_train)

# # Evaluate the model's performance
# y_pred = pipe.predict(X_test)   
# score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)   
# mse = mean_squared_error(y_true=y_test, y_pred=y_pred)
# r2 = r2_score(y_true=y_test, y_pred=y_pred)

# print(f"Mean Squared Error: {mse}")
# print(f"R2 score: {r2}")
# print(f"Testing score: {score}")


# KNeighborsClassifier

# In[ ]:


# from sklearn.datasets import load_iris
# from sklearn.model_selection import GridSearchCV
# from sklearn.pipeline import Pipeline
# from sklearn.preprocessing import StandardScaler
# from sklearn.neighbors import KNeighborsRegressor

# # define a wrapper class for GridSearchCV
# class GridSearchCVWrapper:
#     def __init__(self, model):
#         self.model = model
    
#     def fit(self, X, y, param_grid, cv=5, n_jobs=-1, verbose=2, error_score='raise'):
#         # create pipeline
#         pipe = Pipeline([
#             ('scaler', StandardScaler()),
#             ('clf', self.model)
#         ])
        
#         # perform grid search
#         grid_search = GridSearchCV(pipe, param_grid=param_grid, cv=cv, n_jobs=n_jobs, verbose=verbose, error_score=error_score)
#         grid_search.fit(X, y)
        
#         # return best parameters and score
#         return grid_search.best_params_, grid_search.best_score_

# # load data
# iris = load_iris()
# X = iris.data
# y = iris.target

# # define parameter grid for KNeighborsRegressor
# knn_params = {
#     'clf__n_neighbors': [3, 5, 7, 9],
#     'clf__weights': ['uniform', 'distance'],
#     'clf__algorithm': ['auto', 'ball_tree', 'kd_tree', 'brute'],
#     'clf__leaf_size': [10, 20, 30, 40, 50],
#     'clf__p': [1, 2],
# }

# # perform grid search for KNeighborsClassifier
# knn_wrapper = GridSearchCVWrapper(KNeighborsRegressor())
# knn_best_params, knn_best_score = knn_wrapper.fit(X, y, knn_params)

# # print best parameters and score for KNeighborsRegressor
# print("KNeighborsRegressor:")
# print("Best Parameters:", knn_best_params)
# print("Best Score:", knn_best_score)

# # train model with best parameters on full dataset
# pipe = Pipeline([
#     ('scaler', StandardScaler()),
#     ('clf', KNeighborsRegressor(**{k.replace('clf__', ''): v for k, v in knn_best_params.items()}))
# ])
# pipe.fit(X, y)

# # make predictions on new data
# new_data = [[5.1, 3.5, 1.4, 0.2], [6.2, 2.8, 4.8, 1.8], [7.7, 3.0, 6.1, 2.3]]
# predictions = pipe.predict(new_data)

# print(predictions)


# RandomForestRegressor

# In[ ]:


# from sklearn.model_selection import GridSearchCV
# from sklearn.pipeline import Pipeline
# from sklearn.preprocessing import StandardScaler
# from sklearn.ensemble import RandomForestRegressor

# # define a wrapper class for GridSearchCV
# class GridSearchCVWrapper:
#     def __init__(self, model):
#         self.model = model
    
#     def fit(self, X_train, y_train, param_grid, cv=5, n_jobs=-1, verbose=2, error_score='raise', max_iter=1):
#         # create pipeline
#         pipe = Pipeline([
#             ('scaler', StandardScaler()),
#             ('clf', self.model)
#         ])
        
#         # perform grid search
#         grid_search = GridSearchCV(pipe, param_grid=param_grid, cv=cv, n_jobs=n_jobs, verbose=verbose, error_score=error_score)
#         grid_search.fit(X_train, y_train)
        
#         # set best parameters for the model
#         best_params= {k.replace('clf__', ''): v for k, v in grid_search.best_params_.items()}
#         self.model.set_params(**best_params)
#         # return best parameters and score
#         return grid_search.best_params_, grid_search.best_score_

# # define parameter grid for RandomForestRegressor
# parameters = {
#     'clf__n_estimators': [50, 100, 200],
#     'clf__max_features': ['auto', 'sqrt', 'log2'],
#     'clf__max_depth' : [10, 20, 30, None],
#     'clf__min_samples_split': [2, 5, 10],
#     'clf__min_samples_leaf': [1, 2, 4],
# }

# # perform grid search for RandomForestRegressor
# model = GridSearchCVWrapper(RandomForestRegressor())
# rf_best_params, rf_best_score = model.fit(X_train, y_train, parameters)

# print("RandomForestRegressor:")
# print("Best Parameters:", rf_best_params)
# print("Best Score:", rf_best_score)

# # Evaluate the model's performance
# pipe = Pipeline([
#     ('scaler', StandardScaler()),
#     ('clf', RandomForestRegressor(**{k.replace('clf__', ''): v for k, v in rf_best_params.items()}))
# ])

# # fit pipeline to entire dataset
# pipe.fit(X_train, y_train)

# # predict on new data
# y_pred = pipe.predict(X_test)  
# score = RScore(y_true=y_test, y_pred=y_pred, scoring=scoring)


# ## Using model to make a prediction.

# ### Fitting model to the training set, validating set, and testing set

# In[ ]:


# model = pipe
from sklearn.metrics import explained_variance_score, mean_absolute_error, r2_score, mean_squared_error

def calculate_smape(actual, predicted) -> float:
    # Convert actual and predicted to numpy
    return np.round(
        np.mean(
            np.abs(predicted - actual) / ((np.abs(predicted) + np.abs(actual)))
        ) * 100, 2
    )
def mean_absolute_percentage_error(y_true, y_pred):
    return np.mean(np.abs((y_true - y_pred) / y_true)) * 100
if algorithm =='xgboost':
    y_train_pred = model.predict(xgb.DMatrix(data=X_train))
    # Calculate confusion matrix and classification report for testing dataset
    y_test_pred = model.predict(xgb.DMatrix(data=X_test))
    # Calculate confusion matrix and classification report for validation dataset
    y_val_pred = model.predict(xgb.DMatrix(data=X_valid))
    
    train_preds = y_train_pred #Step 6: Fitting Model to the training set
    valid_preds = y_val_pred #Step 7: Fitting Model To the validation set
    test_preds = y_test_pred #Step 8: Predicting the test set result 
    # prediction = model.predict(df[new_list_feature])

    # df["Prediction"] = prediction
    # df["Prediction"]= np.where(df.Fracture_Intensity == 0,0, prediction)
    # # Spill to individual well
    # for well_name in df.WELL.unique():
    #     wells_df1 = df[df.WELL ==well_name]
    #     # print(wells_df1)
    #     wells_df1.to_csv("/work/Output/results/model_on_all_wells_threshold_"+str(threshold)+"_"+well_name+".csv", index=True)

    #Scoring 
    #Validating
    valid_mse = mean_squared_error(y_valid, valid_preds)
    valid_mape = mean_absolute_percentage_error(y_valid, valid_preds)
    valid_EVS = explained_variance_score(y_valid, valid_preds)
    valid_mae = mean_absolute_error(y_valid, valid_preds)
    valid_rmse = math.sqrt(valid_mse)
    valid_R2 = r2_score(y_valid, valid_preds)
    valid_SMAPE = calculate_smape(y_valid, valid_preds)
    valid_residual = y_valid - valid_preds
    valid_mean_residual = valid_residual.mean()
    #Training
    train_mse = mean_squared_error(y_train, train_preds)
    train_mape = mean_absolute_percentage_error(y_train, train_preds)
    train_EVS = explained_variance_score(y_train, train_preds)
    train_mae = mean_absolute_error(y_train, train_preds)
    train_R2 = r2_score(y_train, train_preds)
    train_SMAPE = calculate_smape(y_train, train_preds)
    train_rmse = math.sqrt(train_mse)
    train_residual=  y_train - train_preds
    train_mean_residual = train_residual.mean()
    #Testing
    test_mse = mean_squared_error(y_test, test_preds)
    test_mape = mean_absolute_percentage_error(y_test, test_preds)
    test_EVS = explained_variance_score(y_test, test_preds)
    test_mae = mean_absolute_error(y_test, test_preds)
    test_R2 = r2_score(y_test, test_preds)
    test_SMAPE = calculate_smape(y_test, test_preds)
    test_rmse = math.sqrt(test_mse)
    test_residual = y_test - test_preds
    test_mean_residual = test_residual.mean()
else:
    y_train_pred = model.predict(X_train)
    y_test_pred = model.predict(X_test)
    y_val_pred = model.predict(X_valid)
    train_preds = y_train_pred #Step 6: Fitting Model to the training set
    valid_preds = y_val_pred #Step 7: Fitting Model To the validation set
    test_preds = y_test_pred #Step 8: Predicting the test set result 
    # prediction = model.predict(df[new_list_feature])

    # df["Prediction"] = prediction
    # df["Prediction"]= np.where(df.Fracture_Intensity == 0,0, prediction)
    # # Spill to individual well
    # for well_name in df.WELL.unique():
    #     wells_df1 = df[df.WELL ==well_name]
    #     # print(wells_df1)
    #     wells_df1.to_csv("/work/Output/results/model_on_all_wells_threshold_"+str(threshold)+"_"+well_name+".csv", index=True)

    #Scoring 
    #Validating
    valid_mse = mean_squared_error(y_valid, valid_preds)
    valid_mape = mean_absolute_percentage_error(y_valid, valid_preds)
    valid_EVS = explained_variance_score(y_valid, valid_preds)
    valid_mae = mean_absolute_error(y_valid, valid_preds)
    valid_rmse = math.sqrt(valid_mse)
    valid_R2 = r2_score(y_valid, valid_preds)
    valid_SMAPE = calculate_smape(y_valid, valid_preds)
    valid_residual = y_valid - valid_preds
    valid_mean_residual = valid_residual.mean()
    #Training
    train_mse = mean_squared_error(y_train, train_preds)
    train_mape = mean_absolute_percentage_error(y_train, train_preds)
    train_EVS = explained_variance_score(y_train, train_preds)
    train_mae = mean_absolute_error(y_train, train_preds)
    train_R2 = r2_score(y_train, train_preds)
    train_SMAPE = calculate_smape(y_train, train_preds)
    train_rmse = math.sqrt(train_mse)
    train_residual=  y_train - train_preds
    train_mean_residual = train_residual.mean()
    #Testing
    test_mse = mean_squared_error(y_test, test_preds)
    test_mape = mean_absolute_percentage_error(y_test, test_preds)
    test_EVS = explained_variance_score(y_test, test_preds)
    test_mae = mean_absolute_error(y_test, test_preds)
    test_R2 = r2_score(y_test, test_preds)
    test_SMAPE = calculate_smape(y_test, test_preds)
    test_rmse = math.sqrt(test_mse)
    test_residual = y_test - test_preds
    test_mean_residual = test_residual.mean()


# ## Plot image

# ### Chart for all wells

# In[37]:


#Validation chart
plt.plot(y_valid,valid_preds,"o", ms=8, mec="b", mfc = "b")
z = np.polyfit(y_valid, valid_preds, 1)
y_hat = np.poly1d(z)(y_valid)
plt.plot(y_valid, y_hat, "r--", lw=1)
text = f"$y={z[0]:0.3f}\;x{z[1]:+0.3f}$\n$R^2 = {r2_score(valid_preds,y_hat):0.3f}$\nRMSE = {valid_rmse:0.3f}\nMAE = {valid_mae:0.3f}\nMR = {valid_mean_residual:0.3f}" \
       f", \nSMAPE = {valid_SMAPE:}%, \nEVS = {valid_EVS:0.3f}"
plt.gca().text(0.05, 0.95, text,transform=plt.gca().transAxes, fontsize=12, verticalalignment='top')
plt.ylabel("Fracture_Intensity_Prediction")
plt.xlabel("Fracture_Intensity_Target")
plt.savefig('/lakehouse/default/Files/Validate.png')
plt.close()

#Training chart
plt.plot(y_train,train_preds,"o", ms=8, mec="b", mfc = "b")
z = np.polyfit(y_train, train_preds, 1)
y_hat = np.poly1d(z)(y_train)
plt.plot(y_train, y_hat, "r--", lw=1)
text = f"$y={z[0]:0.3f}\;x{z[1]:+0.3f}$\n$R^2 = {r2_score(train_preds,y_hat):0.3f}$\nRMSE = {train_rmse:0.3f}\nMAE = {train_mae:0.3f}\nMR = {train_mean_residual:0.3f}\nSMAPE = {train_SMAPE:}%, \nEVS = {train_EVS:0.3f}"
plt.gca().text(0.05, 0.95, text,transform=plt.gca().transAxes, fontsize=12, verticalalignment='top')
plt.ylabel("Fracture_Intensity_Prediction")
plt.xlabel("Fracture_Intensity_Target")
plt.savefig('/lakehouse/default/Files/Training.png')
plt.close()

#Testing chart
plt.plot(y_test,test_preds,"o", ms=8, mec="g", mfc ="g")
z = np.polyfit(y_test, test_preds, 1)
y_hat = np.poly1d(z)(y_test)
plt.plot(y_test, y_hat, ",--", lw=1)
text = f"$y={z[0]:0.3f}\;x{z[1]:+0.3f}$\n$R^2 = {r2_score(test_preds,y_hat):0.3f}$\nRMSE = {test_rmse:0.3f}\nMAE = {test_mae:0.3f}\nMR = {test_mean_residual:0.3f}" \
       f", \nSMAPE = {test_SMAPE:}%, \nEVS = {test_EVS:0.3f}%"
plt.gca().text(0.05, 0.95, text,transform=plt.gca().transAxes, fontsize=12, verticalalignment='top')
plt.ylabel("Fracture_Intensity_Prediction")
plt.xlabel("Fracture_Intensity_Target")
plt.savefig('/lakehouse/default/Files/Testing.png')
plt.close()

#Validation residual
plt.scatter(y=valid_residual, x= y_valid)
plt.axhline(y=0, color='r', linestyle='-')
plt.ylabel("Validate_Residual")
plt.xlabel("Validation_Independent variable")
plt.savefig('/lakehouse/default/Files/Validate_Residual.png')
plt.close()
#Histogram distribution
sns.displot(valid_residual)
plt.xlabel("Validate_Residual")
plt.savefig('/lakehouse/default/Files/Validate_Residual_Historgram.png')
plt.close()
#Training residual
plt.scatter(y=train_residual, x= y_train)
plt.axhline(y=0, color='r', linestyle='-')
plt.ylabel("Training_Residual")
plt.xlabel("Training_Independent variable")
plt.savefig('/lakehouse/default/Files/Training_Residual.png')
plt.close()
#Histogram distribution
sns.displot(train_residual)
plt.xlabel("Training_Residual")
plt.savefig('/lakehouse/default/Files/Training_Residual_Historgram.png')
plt.close()
#Testing residual
plt.scatter(y=test_residual, x= y_test)
plt.axhline(y=0, color='r', linestyle='-')
plt.ylabel("Testing_Residual")
plt.xlabel("Testing_Independent variable")
plt.savefig('/lakehouse/default/Files/Testing_Residual.png')
plt.close()
#Histogram distribution
sns.displot(test_residual)
plt.xlabel("Testing_Residual")
plt.savefig('/lakehouse/default/Files/Testing_Residual_Historgram.png')
plt.close()


# ### Chart for individual category

# In[38]:


## Training data
for well in train_df.WELL.unique():
    train_ = train_df[train_df.WELL==well]
    y_ = train_[Outcome]
    X_ = train_[new_list_feature]
    preprocessors = Pipeline(steps=
        [
            ("imputer", SimpleImputer(strategy='most_frequent')),
            ("scaling", MinMaxScaler())
    ]
    )
    #print(X_train.shape)
    X_ = preprocessors.fit_transform(X_)
    # test_df = preprocessors.transform(test_df)
    train_preds = model.predict(X_)
    plt.plot(y_,train_preds,"o", ms=8, mec="r", mfc = "r")
    z = np.polyfit(y_, train_preds, 1)
    y_hat = np.poly1d(z)(y_)
    plt.plot(y_, y_hat, "r--", lw=1)
    text = f"$y={z[0]:0.3f}\;x{z[1]:+0.3f}$\n$R^2 = {r2_score(train_preds,y_hat):0.3f}$\nRMSE = {math.sqrt(mean_squared_error(y_, train_preds)):0.3f}\nMAE= {mean_absolute_error(y_, train_preds):0.3f}\nMR = {(y_ - train_preds).mean():0.3f} \nSMAPE = {calculate_smape(y_, train_preds):}%, \nEVS= {explained_variance_score(y_, train_preds):0.3f}"
    plt.gca().text(0.05, 0.95, text,transform=plt.gca().transAxes, fontsize=12, verticalalignment='top')
    plt.ylabel("Fracture_Intensity_Prediction")
    plt.xlabel("Fracture_Intensity_Target")
    plt.title(f'{well}', fontsize=12)
    plt.savefig(f'/lakehouse/default/Files/Training_{well}.png')
    plt.close()
## Testing data
for well in test_df.WELL.unique():
    test_ = test_df[test_df.WELL==well]
    y_ = test_[Outcome]
    X_ = test_[new_list_feature]
    preprocessors = Pipeline(steps=
    [
        ("imputer", SimpleImputer(strategy='most_frequent')),
        ("scaling", MinMaxScaler())
    ]
    )
    #print(X_train.shape)
    X_ = preprocessors.transform(X_)

    test_preds = model.predict(X_)
    plt.plot(y_,test_preds,"o", ms=8, mec="b", mfc = "b")
    z = np.polyfit(y_, test_preds, 1)
    y_hat = np.poly1d(z)(y_)
    plt.plot(y_, y_hat, "r--", lw=1)
    text = f"$y={z[0]:0.3f}\;x{z[1]:+0.3f}$\n$R^2 = {r2_score(test_preds,y_hat):0.3f}$\nRMSE = {math.sqrt(mean_squared_error(y_, test_preds)):0.3f}\nMAE= {mean_absolute_error(y_, test_preds):0.3f}\nMR = {(y_ - test_preds).mean():0.3f},\nSMAPE= {calculate_smape(y_, test_preds):}%, \nEVS= {explained_variance_score(y_, test_preds):0.3f}"
    plt.gca().text(0.05, 0.95, text,transform=plt.gca().transAxes, fontsize=12, verticalalignment='top')
    plt.ylabel("Fracture_Intensity_Prediction")
    plt.xlabel("Fracture_Intensity_Target")
    plt.title(f'{well}', fontsize=12)
    plt.savefig(f'/lakehouse/default/Files/Testing_{well}.png')
    plt.close()


# ### Log summary data

# In[ ]:


# run["model_summary"] = create_booster_summary(
#     booster=model,
#     log_trees=True,
#     log_importances=True,
#     list_trees=[0, 1, 2, 3, 4],
#     # log_confusion_matrix=True,
#     # y_pred=valid_preds>=0.5,
#     # y_true=y_test,
# )
# plt.close()


# # Add params to mlflow

# In[39]:


import mlflow
mlflow.autolog(exclusive=False)

mlflow.set_experiment('Experiment_1')

with mlflow.start_run():
  mlflow.log_param(WINDOW_LENGTH) 
  metric_list = ["Window_length","train_mse","train_mape","train_rmse","train_mae","train_R2","train_SMAPE","train_EVS","train_mean_residual","valid_R2","valid_mse","valid_mape","valid_rmse","valid_mae","valid_EVS","valid_mean_residual","valid_SMAPE","test_R2"."test_mse","test_mape","test_rmse","test_mae","test_SMAPE","test_EVS","test_mean_residual"]
  
  # <add model training code here>
  for i in metric_list:  
    mlflow.log_metric(f"{i}", i)

# run["valid_residual"] = valid_residual
# run["train_residual"] = train_residual
# run["test_residual"] = test_residual
# run["Training_Chart"].upload('/work/Output/Figures/Training.png')
# run["Validation_Chart"].upload('/work/Output/Figures/Validate.png')
# run["Testing_Chart"].upload('/work/Output/Figures/Testing.png')
# run["Valid_Residual_Historgram"].upload('/work/Output/Figures/Validate_Residual_Historgram.png')
# run["Train_Residual_Historgram"].upload('/work/Output/Figures/Training_Residual_Historgram.png')
# run["Test_Residual_Historgram"].upload('/work/Output/Figures/Testing_Residual_Historgram.png')
# run["valid_residual"].upload('/work/Output/Figures/Validate_Residual.png')
# run["train_residual"].upload('/work/Output/Figures/Training_Residual.png')
# run["test_residual"].upload('/work/Output/Figures/Testing_Residual.png')
# run["model"].upload("work/Output/Output/Model/model_Goal_3_2.json")
# for well in df.WELL.unique():
#     run[f"Training_Chart_{well}"].upload(f'/work/Output/Figures/Training_{well}.png')
#     run[f"Testing_Chart_{well}"].upload(f'/work/Output/Figures/Testing_{well}.png')
# run["train_data"].upload("/Users/vpi111/Library/CloudStorage/OneDrive-VIENDAUKHIVIETNAM/Goal 3 Fracture identification by WELL LOG data/Sonnt/data/train_data.csv")
# run["blind_data"].upload("/Users/vpi111/Library/CloudStorage/OneDrive-VIENDAUKHIVIETNAM/Goal 3 Fracture identification by WELL LOG data/Sonnt/data/blind_data.csv")
# stop run
run.stop()


# ## Individual depth for visualization

# In[ ]:


Well_list = '15-1-SNS-2P'


# In[ ]:


dataset = df
if Well_list=='all data':
    dataset=dataset.loc[dataset['WELL'] == Well_list]
    dataset = dataset.sort_values(by=['DEPTH'])
else:
    dataset=dataset[dataset["WELL"] == Well_list]
    dataset = dataset.sort_values(by=['DEPTH'])
print('Min dept:',dataset['DEPTH'].min())
print('Max dept:', dataset['DEPTH'].max())


# In[ ]:


From_Depth = '3500'


# In[ ]:


To_Depth = '4000'


# In[ ]:


import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

print(Well_list)
dataset= dataset.loc[(dataset['DEPTH'] <= int(To_Depth))&(dataset['DEPTH'] >= int(From_Depth))]
dataset = dataset.sort_values(by=['DEPTH'])

fig = plt.subplots(figsize=(18,10.3), frameon=True) # facecolor="aliceblue"
plt.tight_layout(pad=0, w_pad=0, h_pad=0, rect=(0.01,0.04,1,0.88))

#Set up the plot axes
ax1 = plt.subplot2grid((1,35), (0,0), rowspan=1, colspan = 4) 
ax2 = plt.subplot2grid((1,35), (0,5), rowspan=1, colspan = 4, sharey = ax1)
ax4 = plt.subplot2grid((1,35), (0,10), rowspan=1, colspan = 4, sharey = ax1)
ax5 = plt.subplot2grid((1,35), (0,15), rowspan=1, colspan = 4, sharey = ax1)
ax6 = plt.subplot2grid((1,35), (0,20), rowspan=1, colspan = 4, sharey = ax1)
# ax7 = plt.subplot2grid((1,35), (0,25), rowspan=1, colspan = 4, sharey = ax1)
# ax10 = plt.subplot2grid((1,35), (0,30), rowspan=1, colspan = 4, sharey = ax1)
ax3 = ax2.twiny()
ax8 = ax4.twiny()
ax9 = ax5.twiny()
ax7 = ax6.twiny()
ax1.plot("GR", "DEPTH", data = dataset, color = "red", linewidth=0.5) # Call the data from the well dataframe
ax1.set_xlabel("GR, gAPI",fontweight='bold') # Assign a track title
ax1.set_xlim(0, 250)
ax1.xaxis.label.set_color("red")
ax1.set_ylabel("Depth (m)")
ax1.tick_params(axis='x', colors="red")
ax1.spines["top"].set_edgecolor("red")
ax1.title.set_color('red')
ax1.set_xticks([0, 50, 100, 150, 200, 250])
ax1.grid() # Display the grid
ax1.invert_yaxis()

ax2.plot("LLD", "DEPTH", data = dataset, color = "green", linewidth=0.5)
ax2.set_xlabel("LLD, Ohm.m",fontweight='bold')
ax2.xaxis.label.set_color("green")
ax2.tick_params(axis='x', colors="green")
ax2.spines["top"].set_position(("axes", 1.02))
ax2.spines["top"].set_edgecolor("green")
ax2.spines["top"].set_visible(True)
ax2.set_xticks([0.1, 1, 10, 100, 1000])
ax2.semilogx()
ax2.grid()

ax3.plot("LLS", "DEPTH", data = dataset, color = "cyan", linewidth=0.5)
ax3.set_xlabel("LLS, Ohm.m",fontweight='bold')
ax3.xaxis.label.set_color("cyan")
ax3.tick_params(axis='x', colors="cyan")
ax3.spines["top"].set_position(("axes", 1.08))
ax3.spines["top"].set_edgecolor("cyan")
ax3.set_xticks([0.1, 1, 10, 100, 1000])
ax3.semilogx()
ax3.grid()


ax4.plot("NPHI", "DEPTH", data = dataset, color = "dodgerblue", linewidth=0.5)
ax4.set_xlabel("NPHI, m3/m3",fontweight='bold')
ax4.xaxis.label.set_color("dodgerblue")
ax4.set_xlim(0, 0.4)
ax4.tick_params(axis='x', colors="dodgerblue")
ax4.spines["top"].set_position(("axes", 1.08))
ax4.spines["top"].set_visible(True)
ax4.spines["top"].set_edgecolor("dodgerblue")
ax4.set_xticks([0., 0.2, 0.4])
ax4.grid()


ax8.plot("RHOB", "DEPTH", data = dataset, color = "darkred", linewidth=0.5)
ax8.set_xlabel("RHOB, g/cm3",fontweight='bold')
ax8.set_xlim(1.95, 2.95)
ax8.xaxis.label.set_color("darkred")
ax8.tick_params(axis='x', colors="darkred")
ax8.spines["top"].set_edgecolor("darkred")
ax8.spines["top"].set_position(("axes", 1.08))
ax8.set_xticks([1.95, 2.45, 2.95])
ax8.grid()


ax5.plot("DTC", "DEPTH", data = dataset, color = "black", linewidth=0.5)
ax5.set_xlabel("DTC, us/ft",fontweight='bold')
ax5.xaxis.label.set_color("black")
ax5.set_xlim(40, 80)
ax5.tick_params(axis='x', colors="black")
ax5.spines["top"].set_position(("axes", 1.02))
ax5.spines["top"].set_visible(True)
ax5.spines["top"].set_edgecolor("black")
ax5.set_xticks([40, 50, 60, 70, 80])
ax5.grid()


ax9.plot("DTS", "DEPTH", data = dataset, color = "orchid", linewidth=0.5)
ax9.set_xlabel("DTS, us/ft",fontweight='bold')
ax9.set_xlim(80, 120)
ax9.xaxis.label.set_color("orchid")
ax9.tick_params(axis='x', colors="orchid")
ax9.spines["top"].set_edgecolor("orchid")
ax9.spines["top"].set_position(("axes", 1.08))
ax9.set_xticks([80, 90, 100, 110, 120])
ax9.grid()

ax6.plot("Fracture_Intensity", "DEPTH", data = dataset, color = "indigo", linewidth=0.5)
ax6.set_xlabel("Fracture_Intensity",fontweight='bold')
ax6.set_xlim(0,5)
ax6.xaxis.label.set_color("indigo")
ax6.tick_params(axis='x', colors="indigo")
ax6.spines["top"].set_edgecolor("indigo")
ax6.spines["top"].set_position(("axes", 1.02))
ax6.set_xticks([0, 1, 2, 3, 4, 5])
# ax6.fill_betweenx(dataset['DEPTH'], dataset['Fracture_Intensity'], 0, facecolor='indigo')
ax6.grid()


ax7.plot("FRACTURE_INTENSITY_PRED", "DEPTH", data = dataset, color = "limegreen", linewidth=0.5)
ax7.set_xlabel("FRACTURE_INTENSITY_PRED",fontweight='bold')
ax7.set_xlabel("FRACTURE_INTENSITY_PRED",fontweight='bold')
ax7.set_xlim(0,5)
ax7.xaxis.label.set_color("limegreen")
ax7.tick_params(axis='x', colors="limegreen")
ax7.spines["top"].set_edgecolor("limegreen")
ax7.spines["top"].set_position(("axes", 1.08))
ax7.set_xticks([0, 1, 2, 3, 4, 5])
# ax7.fill_betweenx(dataset['DEPTH'], dataset['FRACTURE_INTENSITY_PRED'], 0, facecolor='limegreen')
ax7.grid()


# ax10.plot("FRACTURE_ZONE_PRED", "DEPTH", data = dataset2, color = "red", linewidth=0.5)
# ax10.set_xlabel("FRACTURE_PREDICTION",fontweight='bold')
# ax10.set_xlabel("FRACTURE_ZONE_PRED_RF",fontweight='bold')
# ax10.set_xlim(0, 1)
# ax10.xaxis.label.set_color("red")
# ax10.tick_params(axis='x', colors="red")
# ax10.spines["top"].set_edgecolor("red")
# ax10.spines["top"].set_position(("axes", 1.02))
# ax10.set_xticks([0, 0.5, 1])
# ax10.fill_betweenx(dataset2['DEPTH'], dataset2['FRACTURE_ZONE_PRED'], 0, facecolor='red')
# ax10.grid()


for ax in [ax1, ax2, ax4, ax5, 
ax6, 
# ax7,
# ax10
]:
    ax.grid(which='major', color='lightgrey', linestyle='-')
    ax.xaxis.set_ticks_position("top")
    ax.xaxis.set_label_position("top")
    ax.spines["top"].set_position(("axes", 1.02))

for ax in [ax1, ax2, ax4, ax5, 
ax6, 
# ax7, 
# ax10
]:
    plt.setp(ax.get_yticklabels(), visible = True)
# plt.tight_layout()
plt.show()
