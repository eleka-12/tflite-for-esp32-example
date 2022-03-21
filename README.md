# tflite-for-esp32-example

- Step 1 
       > Create a model which you want to use in your controller.
- Step 2
       > After building the model using keras/tensorflow 
       
       > Convert the model in to tflite by using below commands
        
        converter = tf.lite.TFLiteConverter.from_keras_model(model)
        converter.optimizations = [tf.lite.Optimize.OPTIMIZE_FOR_SIZE]
        tflite_model = converter.convert()

       > Save the model to disk
        
        open("sine_model_quantized.tflite", "wb").write(tflite_model)
