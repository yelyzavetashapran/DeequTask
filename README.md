# DeequTask

Hi! It's my realization on Deequ task for program DQE Intermediate Level.

# How to run

1. Set up environment:

  1.1. Install Docker on Windows https://docs.docker.com/desktop/windows/install/
  
  1.2. Clone repository https://github.com/jupyter/docker-stacks
  
  1.3. Rebuild docker "pyspark-notebook" image to support spark 3.0.0 version for PyDeequ needs according to instructions: https://jupyter-docker-stacks.readthedocs.io/en/latest/using/specifics.html
  
  "docker build --rm --force-rm -t jupyter/pyspark-notebook:spark-3.0.0 C:/Users/Yelyzaveta_Shapran/Desktop/docker-stacks/pyspark-notebook --build-arg spark_version=3.0.0 --build-arg hadoop_version=3.2 --build-arg spark_checksum=BFE45406C67CC4AE00411AD18CC438F51E7D4B6F14EB61E7BF6B5450897C2E8D3AB020152657C0239F253735C263512FFABF538AC5B9FFFA38B8295736A9C387 --build-arg openjdk_version=8"

  1.4. Run rebuilt docker image:
  
  "docker run -v {path on your PC to this folder}/docker-stacks:/home/jovyan/work -p 8888:8888 -p 4040:4040 --user root -e JUPYTER_ENABLE_LAB=yes --name pyspark {Docker image id of yours}"
  
  1.5. Copy nessessary JDBC driver to running Docker container (mssql-jdbc-12.2.0.jre8.jar)
  
  1.6. Install pydequ via pip on docker container.
  
  1.7. You should create user in MSSMS and create 'TRN' database (you can find hints for that in my https://github.com/yelyzavetashapran/RobotFramework project).
  
2. Run script:

  2.1. Download and open Deequ_pySpark_skeleton.ipynb.
  
  2.2. If you have different path to JDBC driver, you should change path here:

![image](https://user-images.githubusercontent.com/104168878/234368941-907c435c-040f-4afb-9772-961dd17d5d5c.png)
  
  2.3. Change Config variables:
  
![image](https://user-images.githubusercontent.com/104168878/234369879-073edbab-3169-4e3a-a34b-e9582d07d295.png)

  2.4. Run cells one-by-one to see results.

# Report for constraints verification step:

![image](https://user-images.githubusercontent.com/104168878/234371314-f8d78f35-2005-4588-9f12-d62bb70a2149.png)

That's it! Thank you for your attention!
