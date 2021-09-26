# rdma-examples

gcc -o rping rping.c common.c -libverbs  -lrdmacm  -pthread
gcc -o rdma_server  rdma_server.c -libverbs  -lrdmacm 
gcc -o rdma_client  rdma_client.c -libverbs  -lrdmacm 
