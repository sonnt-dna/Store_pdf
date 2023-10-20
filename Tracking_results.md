ML flow workflow
MLflow Tracking là một API và UI để có thể lưu các parameters, code, metrics, và output và so sánh các mô hình dự báo giữa các lần chạy khác nhau.

MLflow Tracking có thể được sử dụng để lưu các mô hình trên các nền tảng:

Local
MS Fabric
DagsHub
Azure Machine Learning
Đây là notebook mẫu về các bước để có thể sử dụng MLflow Tracking trên Experiment trên MS Fabric workspace. Người dùng phải chỉnh sửa để phù hợp với mong muốn của bản thân
Link tham khảo: https://app.powerbi.com/links/-DRD_JtxcN?ctid=c5ec5abe-76c1-46cb-b3fe-c3b0071ffdb3&pbi_source=linkShare&ctid=c5ec5abe-76c1-46cb-b3fe-c3b0071ffdb3&experience=data-science

Tài liệu tham khảo: https://mlflow.org/docs/latest/tracking.html#logging-functions
Code hướng dẫn demo:

  Tham số nên thay đổi:
  
  run_name: Tên của lần chạy mới. Chỉ được sử dụng khi run_id không được chỉ định.
  Logging: {
  
  '.set_tag': Đặt tag cho lần chạy hiện tại. Nếu không có lần chạy nào đang hoạt động, phương thức này sẽ tạo ra một lần chạy mới.
  
  '.log_params': Lưu giá trị các tham số (parameters)
  
  '.log_metrics': Lưu giá trị các số liệu đánh giá (evaluation metrics) cho lần chạy hiện tại
  }
  def lstm2layers_mlflow_run(
    name,
    lstm_params,
    train_params,
    val_split_params,
    train_dataset,
    train_dataset_,
    test_dataset,
    y_test,
):
    with mlflow.start_run(run_name=name):
        mlflow.log_params(lstm_params)
        mlflow.log_params(train_params)
        # mlflow.log_param('', val_split_params)
        mlflow.set_tag("model_name", "LSTM_2layers")

        lstm = build_lstm_2layers(lstm_params)
        lstm = train_lstm(lstm, train_params, train_dataset, train_dataset_, val_split_params)

        test_preds = lstm.predict(test_dataset)
        test_preds = scaler.inverse_transform(test_preds)

        test_rms = mean_squared_error(
            y_test, test_preds.ravel(), squared=False
        )
        mlflow.log_metric("test_rmse", test_rms)
        mlflow.tensorflow.log_model(lstm, "tf_models")
