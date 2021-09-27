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
 
 ![image](https://user-images.githubusercontent.com/42670639/134877374-6543d0f5-9ba8-4258-b61c-30bbb9399a7d.png)

    
![image](https://user-images.githubusercontent.com/42670639/134877475-102762ef-05e4-4da3-8c98-3690439a7cd7.png)



![image](https://user-images.githubusercontent.com/42670639/134877149-6e751a4d-5c7d-492f-b91c-d190ee2f6178.png)
