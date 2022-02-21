Benchmark
=========

`smartctl /dev/nvme0n1 -a`

`dd if=/dev/zero of=./temp-image.img bs=4M`

`iostat -t 1`

`sudo fio --name=write_iops --directory=$TEST_DIR --size=10G \
--time_based --runtime=60s --ramp_time=2s --ioengine=libaio --direct=1 \
--verify=0 --bs=4K --iodepth=64 --rw=randwrite --group_reporting=1`	# random write IOPS, using I/O block 4kb and I/O depth 64

`sudo fio --name=read_throughput --directory=$TEST_DIR --numjobs=8 \
--size=10G --time_based --runtime=60s --ramp_time=2s --ioengine=libaio \
--direct=1 --verify=0 --bs=1M --iodepth=64 --rw=read \
--group_reporting=1`	# read throughput using sequential read with 8 parallel streams, I/O block 1MB, I/O depth 64

[back](./)

