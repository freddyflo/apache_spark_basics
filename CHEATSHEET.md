# Apache Spark Basics


### Run Spark interactively in python interpreter


```sh
$ ./bin/pyspark --master  "local[2]"
```

```sh
Python 3.11.6 (v3.11.6:8b6ee5ba3b, Oct  2 2023, 11:18:21) [Clang 13.0.0 (clang-1300.0.29.30)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
Setting default log level to "WARN".
To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
24/07/26 11:23:30 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /__ / .__/\_,_/_/ /_/\_\   version 3.5.1
      /_/

Using Python version 3.11.6 (v3.11.6:8b6ee5ba3b, Oct  2 2023 11:18:21)
Spark context Web UI available at http://mbp-de-fred.lan:4040
Spark context available as 'sc' (master = local[2], app id = local-1721985811199).
SparkSession available as 'spark'.
```

### Run sample applications 

```sh
./bin/spark-submit examples/src/main/python/pi.py 10
```

```sh
24/07/26 11:29:27 INFO SparkContext: Running Spark version 3.5.1
24/07/26 11:29:27 INFO SparkContext: OS info Mac OS X, 14.5, x86_64
24/07/26 11:29:27 INFO SparkContext: Java version 18.0.2
24/07/26 11:29:27 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
24/07/26 11:29:27 INFO ResourceUtils: ==============================================================
24/07/26 11:29:27 INFO ResourceUtils: No custom resources configured for spark.driver.
24/07/26 11:29:27 INFO ResourceUtils: ==============================================================
24/07/26 11:29:27 INFO SparkContext: Submitted application: PythonPi
24/07/26 11:29:27 INFO ResourceProfile: Default ResourceProfile created, executor resources: Map(cores -> name: cores, amount: 1, script: , vendor: , memory -> name: memory, amount: 1024, script: , vendor: , offHeap -> name: offHeap, amount: 0, script: , vendor: ), task resources: Map(cpus -> name: cpus, amount: 1.0)
24/07/26 11:29:27 INFO ResourceProfile: Limiting resource is cpu
24/07/26 11:29:27 INFO ResourceProfileManager: Added ResourceProfile id: 0
24/07/26 11:29:27 INFO SecurityManager: Changing view acls to: aklamanu
24/07/26 11:29:27 INFO SecurityManager: Changing modify acls to: aklamanu
24/07/26 11:29:27 INFO SecurityManager: Changing view acls groups to:
24/07/26 11:29:27 INFO SecurityManager: Changing modify acls groups to:
24/07/26 11:29:27 INFO SecurityManager: SecurityManager: authentication disabled; ui acls disabled; users with view permissions: aklamanu; groups with view permissions: EMPTY; users with modify permissions: aklamanu; groups with modify permissions: EMPTY
24/07/26 11:29:28 INFO Utils: Successfully started service 'sparkDriver' on port 52079.
24/07/26 11:29:28 INFO SparkEnv: Registering MapOutputTracker
24/07/26 11:29:28 INFO SparkEnv: Registering BlockManagerMaster
24/07/26 11:29:28 INFO BlockManagerMasterEndpoint: Using org.apache.spark.storage.DefaultTopologyMapper for getting topology information
24/07/26 11:29:28 INFO BlockManagerMasterEndpoint: BlockManagerMasterEndpoint up
24/07/26 11:29:28 INFO SparkEnv: Registering BlockManagerMasterHeartbeat
24/07/26 11:29:28 INFO DiskBlockManager: Created local directory at /private/var/folders/gh/hnjdv1z15clbrfz9f7shfy940000gn/T/blockmgr-be2c0bd5-ae0f-4db9-a90a-fad96191dde0
24/07/26 11:29:28 INFO MemoryStore: MemoryStore started with capacity 434.4 MiB
24/07/26 11:29:28 INFO SparkEnv: Registering OutputCommitCoordinator
24/07/26 11:29:28 INFO JettyUtils: Start Jetty 0.0.0.0:4040 for SparkUI
24/07/26 11:29:28 WARN Utils: Service 'SparkUI' could not bind on port 4040. Attempting port 4041.
24/07/26 11:29:28 INFO Utils: Successfully started service 'SparkUI' on port 4041.
24/07/26 11:29:28 INFO Executor: Starting executor ID driver on host mbp-de-fred.lan
24/07/26 11:29:28 INFO Executor: OS info Mac OS X, 14.5, x86_64
24/07/26 11:29:28 INFO Executor: Java version 18.0.2
24/07/26 11:29:28 INFO Executor: Starting executor with user classpath (userClassPathFirst = false): ''
24/07/26 11:29:28 INFO Executor: Created or updated repl class loader org.apache.spark.util.MutableURLClassLoader@6288ea99 for default.
24/07/26 11:29:28 INFO Utils: Successfully started service 'org.apache.spark.network.netty.NettyBlockTransferService' on port 52080.
24/07/26 11:29:28 INFO NettyBlockTransferService: Server created on mbp-de-fred.lan:52080
24/07/26 11:29:28 INFO BlockManager: Using org.apache.spark.storage.RandomBlockReplicationPolicy for block replication policy
24/07/26 11:29:28 INFO BlockManagerMaster: Registering BlockManager BlockManagerId(driver, mbp-de-fred.lan, 52080, None)
24/07/26 11:29:28 INFO BlockManagerMasterEndpoint: Registering block manager mbp-de-fred.lan:52080 with 434.4 MiB RAM, BlockManagerId(driver, mbp-de-fred.lan, 52080, None)
24/07/26 11:29:28 INFO BlockManagerMaster: Registered BlockManager BlockManagerId(driver, mbp-de-fred.lan, 52080, None)
24/07/26 11:29:28 INFO BlockManager: Initialized BlockManager: BlockManagerId(driver, mbp-de-fred.lan, 52080, None)
24/07/26 11:29:29 INFO SparkContext: Starting job: reduce at /Users/aklamanu/Downloads/spark-3.5.1-bin-hadoop3/examples/src/main/python/pi.py:42
24/07/26 11:29:29 INFO DAGScheduler: Got job 0 (reduce at /Users/aklamanu/Downloads/spark-3.5.1-bin-hadoop3/examples/src/main/python/pi.py:42) with 10 output partitions
24/07/26 11:29:29 INFO DAGScheduler: Final stage: ResultStage 0 (reduce at /Users/aklamanu/Downloads/spark-3.5.1-bin-hadoop3/examples/src/main/python/pi.py:42)
24/07/26 11:29:29 INFO DAGScheduler: Parents of final stage: List()
24/07/26 11:29:29 INFO DAGScheduler: Missing parents: List()
24/07/26 11:29:29 INFO DAGScheduler: Submitting ResultStage 0 (PythonRDD[1] at reduce at /Users/aklamanu/Downloads/spark-3.5.1-bin-hadoop3/examples/src/main/python/pi.py:42), which has no missing parents
24/07/26 11:29:29 INFO MemoryStore: Block broadcast_0 stored as values in memory (estimated size 12.5 KiB, free 434.4 MiB)
24/07/26 11:29:29 INFO MemoryStore: Block broadcast_0_piece0 stored as bytes in memory (estimated size 9.3 KiB, free 434.4 MiB)
24/07/26 11:29:29 INFO BlockManagerInfo: Added broadcast_0_piece0 in memory on mbp-de-fred.lan:52080 (size: 9.3 KiB, free: 434.4 MiB)
24/07/26 11:29:29 INFO SparkContext: Created broadcast 0 from broadcast at DAGScheduler.scala:1585
24/07/26 11:29:29 INFO DAGScheduler: Submitting 10 missing tasks from ResultStage 0 (PythonRDD[1] at reduce at /Users/aklamanu/Downloads/spark-3.5.1-bin-hadoop3/examples/src/main/python/pi.py:42) (first 15 tasks are for partitions Vector(0, 1, 2, 3, 4, 5, 6, 7, 8, 9))
24/07/26 11:29:29 INFO TaskSchedulerImpl: Adding task set 0.0 with 10 tasks resource profile 0
24/07/26 11:29:29 INFO TaskSetManager: Starting task 0.0 in stage 0.0 (TID 0) (mbp-de-fred.lan, executor driver, partition 0, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 1.0 in stage 0.0 (TID 1) (mbp-de-fred.lan, executor driver, partition 1, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 2.0 in stage 0.0 (TID 2) (mbp-de-fred.lan, executor driver, partition 2, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 3.0 in stage 0.0 (TID 3) (mbp-de-fred.lan, executor driver, partition 3, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 4.0 in stage 0.0 (TID 4) (mbp-de-fred.lan, executor driver, partition 4, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 5.0 in stage 0.0 (TID 5) (mbp-de-fred.lan, executor driver, partition 5, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 6.0 in stage 0.0 (TID 6) (mbp-de-fred.lan, executor driver, partition 6, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 7.0 in stage 0.0 (TID 7) (mbp-de-fred.lan, executor driver, partition 7, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 8.0 in stage 0.0 (TID 8) (mbp-de-fred.lan, executor driver, partition 8, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO TaskSetManager: Starting task 9.0 in stage 0.0 (TID 9) (mbp-de-fred.lan, executor driver, partition 9, PROCESS_LOCAL, 7595 bytes)
24/07/26 11:29:29 INFO Executor: Running task 8.0 in stage 0.0 (TID 8)
24/07/26 11:29:29 INFO Executor: Running task 9.0 in stage 0.0 (TID 9)
24/07/26 11:29:29 INFO Executor: Running task 7.0 in stage 0.0 (TID 7)
24/07/26 11:29:29 INFO Executor: Running task 0.0 in stage 0.0 (TID 0)
24/07/26 11:29:29 INFO Executor: Running task 6.0 in stage 0.0 (TID 6)
24/07/26 11:29:29 INFO Executor: Running task 3.0 in stage 0.0 (TID 3)
24/07/26 11:29:29 INFO Executor: Running task 2.0 in stage 0.0 (TID 2)
24/07/26 11:29:29 INFO Executor: Running task 1.0 in stage 0.0 (TID 1)
24/07/26 11:29:29 INFO Executor: Running task 5.0 in stage 0.0 (TID 5)
24/07/26 11:29:29 INFO Executor: Running task 4.0 in stage 0.0 (TID 4)
24/07/26 11:29:30 INFO PythonRunner: Times: total = 937, boot = 646, init = 179, finish = 112
24/07/26 11:29:30 INFO PythonRunner: Times: total = 946, boot = 652, init = 176, finish = 118
24/07/26 11:29:30 INFO PythonRunner: Times: total = 950, boot = 664, init = 170, finish = 116
24/07/26 11:29:30 INFO Executor: Finished task 0.0 in stage 0.0 (TID 0). 1412 bytes result sent to driver
24/07/26 11:29:30 INFO Executor: Finished task 5.0 in stage 0.0 (TID 5). 1412 bytes result sent to driver
24/07/26 11:29:30 INFO PythonRunner: Times: total = 966, boot = 657, init = 189, finish = 120
24/07/26 11:29:30 INFO Executor: Finished task 3.0 in stage 0.0 (TID 3). 1369 bytes result sent to driver
24/07/26 11:29:30 INFO Executor: Finished task 2.0 in stage 0.0 (TID 2). 1412 bytes result sent to driver
24/07/26 11:29:30 INFO PythonRunner: Times: total = 979, boot = 680, init = 173, finish = 126
24/07/26 11:29:30 INFO TaskSetManager: Finished task 2.0 in stage 0.0 (TID 2) in 1096 ms on mbp-de-fred.lan (executor driver) (1/10)
24/07/26 11:29:30 INFO TaskSetManager: Finished task 3.0 in stage 0.0 (TID 3) in 1098 ms on mbp-de-fred.lan (executor driver) (2/10)
24/07/26 11:29:30 INFO TaskSetManager: Finished task 0.0 in stage 0.0 (TID 0) in 1115 ms on mbp-de-fred.lan (executor driver) (3/10)
24/07/26 11:29:30 INFO TaskSetManager: Finished task 5.0 in stage 0.0 (TID 5) in 1097 ms on mbp-de-fred.lan (executor driver) (4/10)
24/07/26 11:29:30 INFO Executor: Finished task 4.0 in stage 0.0 (TID 4). 1369 bytes result sent to driver
24/07/26 11:29:30 INFO TaskSetManager: Finished task 4.0 in stage 0.0 (TID 4) in 1100 ms on mbp-de-fred.lan (executor driver) (5/10)
24/07/26 11:29:30 INFO PythonRunner: Times: total = 986, boot = 672, init = 182, finish = 132
24/07/26 11:29:30 INFO PythonAccumulatorV2: Connected to AccumulatorServer at host: 127.0.0.1 port: 52082
24/07/26 11:29:30 INFO Executor: Finished task 6.0 in stage 0.0 (TID 6). 1369 bytes result sent to driver
24/07/26 11:29:30 INFO TaskSetManager: Finished task 6.0 in stage 0.0 (TID 6) in 1104 ms on mbp-de-fred.lan (executor driver) (6/10)
24/07/26 11:29:30 INFO PythonRunner: Times: total = 1006, boot = 704, init = 171, finish = 131
24/07/26 11:29:30 INFO Executor: Finished task 9.0 in stage 0.0 (TID 9). 1369 bytes result sent to driver
24/07/26 11:29:30 INFO TaskSetManager: Finished task 9.0 in stage 0.0 (TID 9) in 1123 ms on mbp-de-fred.lan (executor driver) (7/10)
24/07/26 11:29:30 INFO PythonRunner: Times: total = 1012, boot = 693, init = 178, finish = 141
24/07/26 11:29:30 INFO Executor: Finished task 1.0 in stage 0.0 (TID 1). 1412 bytes result sent to driver
24/07/26 11:29:30 INFO TaskSetManager: Finished task 1.0 in stage 0.0 (TID 1) in 1139 ms on mbp-de-fred.lan (executor driver) (8/10)
24/07/26 11:29:30 INFO PythonRunner: Times: total = 1023, boot = 716, init = 169, finish = 138
24/07/26 11:29:30 INFO PythonRunner: Times: total = 1027, boot = 729, init = 160, finish = 138
24/07/26 11:29:30 INFO Executor: Finished task 8.0 in stage 0.0 (TID 8). 1369 bytes result sent to driver
24/07/26 11:29:30 INFO Executor: Finished task 7.0 in stage 0.0 (TID 7). 1369 bytes result sent to driver
24/07/26 11:29:30 INFO TaskSetManager: Finished task 8.0 in stage 0.0 (TID 8) in 1142 ms on mbp-de-fred.lan (executor driver) (9/10)
24/07/26 11:29:30 INFO TaskSetManager: Finished task 7.0 in stage 0.0 (TID 7) in 1144 ms on mbp-de-fred.lan (executor driver) (10/10)
24/07/26 11:29:30 INFO TaskSchedulerImpl: Removed TaskSet 0.0, whose tasks have all completed, from pool
24/07/26 11:29:30 INFO DAGScheduler: ResultStage 0 (reduce at /Users/aklamanu/Downloads/spark-3.5.1-bin-hadoop3/examples/src/main/python/pi.py:42) finished in 1.663 s
24/07/26 11:29:30 INFO DAGScheduler: Job 0 is finished. Cancelling potential speculative or zombie tasks for this job
24/07/26 11:29:30 INFO TaskSchedulerImpl: Killing all running tasks in stage 0: Stage finished
24/07/26 11:29:30 INFO DAGScheduler: Job 0 finished: reduce at /Users/aklamanu/Downloads/spark-3.5.1-bin-hadoop3/examples/src/main/python/pi.py:42, took 1.698488 s
Pi is roughly 3.149680
24/07/26 11:29:31 INFO SparkContext: SparkContext is stopping with exitCode 0.
24/07/26 11:29:31 INFO SparkUI: Stopped Spark web UI at http://mbp-de-fred.lan:4041
24/07/26 11:29:31 INFO MapOutputTrackerMasterEndpoint: MapOutputTrackerMasterEndpoint stopped!
24/07/26 11:29:31 INFO MemoryStore: MemoryStore cleared
24/07/26 11:29:31 INFO BlockManager: BlockManager stopped
24/07/26 11:29:31 INFO BlockManagerMaster: BlockManagerMaster stopped
24/07/26 11:29:31 INFO OutputCommitCoordinator$OutputCommitCoordinatorEndpoint: OutputCommitCoordinator stopped!
24/07/26 11:29:31 INFO SparkContext: Successfully stopped SparkContext
24/07/26 11:29:31 INFO ShutdownHookManager: Shutdown hook called
24/07/26 11:29:31 INFO ShutdownHookManager: Deleting directory /private/var/folders/gh/hnjdv1z15clbrfz9f7shfy940000gn/T/spark-f072e44c-d310-4019-8549-84bf0ea6e787
24/07/26 11:29:31 INFO ShutdownHookManager: Deleting directory /private/var/folders/gh/hnjdv1z15clbrfz9f7shfy940000gn/T/spark-dc451c99-22ad-4f2e-9830-6226c215d28d/pyspark-924a881c-99cb-44ff-b7ab-a7e898bdb64e
24/07/26 11:29:31 INFO ShutdownHookManager: Deleting directory /private/var/folders/gh/hnjdv1z15clbrfz9f7shfy940000gn/T/spark-dc451c99-22ad-4f2e-9830-6226c215d28d
```