# rdma-examples

gcc -o rping rping.c common.c -libverbs  -lrdmacm  -pthread

gcc -o rdma_server  rdma_server.c -libverbs  -lrdmacm 

gcc -o rdma_client  rdma_client.c -libverbs  -lrdmacm 


server:
./rping -s -a 10.228.74.228 -p 5000 -v
client:
./rping -c -a 10.228.74.228 -p 5000 -v


server:
./rdma_server -s 10.228.74.228 -p 5000
client:
./rdma_client -s 10.228.74.228 -p 5000

client:
ibv_rc_pingpong -g 0 -d mlx5_0 -i 1
server:
ibv_rc_pingpong -g 0 -d mlx5_0 -i 1  10.228.74.215


server:
 ./ib_send_bw
 ./ib_send_bw
 ./ib_send_lat
 
 client:
 ./ib_send_bw 10.228.74.215  --report_gbits -F
  ./ib_send_bw 10.228.74.215  --report_gbits -F
 ./ib_send_lat 10.228.74.215  --report_gbits -F
 
 device select：
 [root@snat01 bin]# ibv_devices
    device                 node GUID
    ------              ----------------
    mlx5_0              043f720300c10530
    mlx5_1              043f720300c10531
[root@snat01 bin]# ibv_devinfo
hca_id: mlx5_0
        transport:                      InfiniBand (0)
        fw_ver:                         16.28.1002
        node_guid:                      043f:7203:00c1:0530
        sys_image_guid:                 043f:7203:00c1:0530
        vendor_id:                      0x02c9
        vendor_part_id:                 4119
        hw_ver:                         0x0
        board_id:                       MT_0000000080
        phys_port_cnt:                  1
                port:   1
                        state:                  PORT_ACTIVE (4)
                        max_mtu:                4096 (5)
                        active_mtu:             1024 (3)
                        sm_lid:                 0
                        port_lid:               0
                        port_lmc:               0x00
                        link_layer:             Ethernet

hca_id: mlx5_1
        transport:                      InfiniBand (0)
        fw_ver:                         16.28.1002
        node_guid:                      043f:7203:00c1:0531
        sys_image_guid:                 043f:7203:00c1:0530
        vendor_id:                      0x02c9
        vendor_part_id:                 4119
        hw_ver:                         0x0
        board_id:                       MT_0000000080
        phys_port_cnt:                  1
                port:   1
                        state:                  PORT_ACTIVE (4)
                        max_mtu:                4096 (5)
                        active_mtu:             1024 (3)
                        sm_lid:                 0
                        port_lid:               0
                        port_lmc:               0x00
                        link_layer:             Ethernet

[root@snat01 bin]# 


![image](https://user-images.githubusercontent.com/42670639/134877149-6e751a4d-5c7d-492f-b91c-d190ee2f6178.png)
