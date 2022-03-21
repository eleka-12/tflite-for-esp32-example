# tflite-for-esp32-example

- Step 1 
        Create a model which you want to use in your controller.
- Step 2
        After building the model using keras/tensorflow 
       
        Convert the model in to tflite by using below commands
        
        converter = tf.lite.TFLiteConverter.from_keras_model(model)
        converter.optimizations = [tf.lite.Optimize.OPTIMIZE_FOR_SIZE]
        tflite_model = converter.convert()

        Save the model to disk
        
        open("model_name.tflite", "wb").write(tflite_model)
        
- Step 3
        Use this command in your linux machine/git bash to convert tflite into .cc model
        
        >xxd -i model_name.tflite > model_name.cc
- Step 4
        Array will be generated from .cc file which will be used as a .header file 
    
