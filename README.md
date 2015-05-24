# CI MULTIPART LIBRARY

### Version
1.0.0


>Code igniter tiene un problema cuando queremos agregar archivos de forma masiva o multipart
>esta libreria soluciona tal error


Ejemplo de multipart:

        <?php echo form_open_multipart("fileupload/upload/"); ?>
        <input type="file" name="myfile[]"><br>
        <input type="file" name="myfile[]"><br>
        <input type="file" name="myfile[]"><br>
        <input type="submit" value="Upload File to Server">
        <?php echo form_close(); ?>



### Uso de libreria
        $this->load->library("base_upload"); //mandamos a llamar la libreria
        $this->base_upload->set_path('./file_test/'); //colocamos la ruta donde se guardaran los                archivos
        $this->load->helper('string'); //libreria opcional 
        
        //Opcional : cambiandole nombres a los documentos antes de guardarlos
        $data1 =  random_string();
        $data2 = random_string("sha1");
        $data3 = random_string("md5");
        
        $this->base_upload->set_filename(array(
            $data1,
            $data2,
            $data3 
        ));
        
         $this->base_upload->Do_MultiUpload('myfile'); //guardamos los documentos



