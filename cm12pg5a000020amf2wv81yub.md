---
title: "Deployed a polling app with kind and argo cd with continuous monitoring by kubernetes dashboard."
datePublished: Sat Sep 14 2024 22:14:28 GMT+0000 (Coordinated Universal Time)
cuid: cm12pg5a000020amf2wv81yub
slug: deployed-a-polling-app-with-kind-and-argo-cd-with-continuous-monitoring-by-kubernetes-dashboard

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351775322/7a987a21-d0d5-400d-b5cb-3ebc0d7ff076.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351781300/e37d707f-1a89-4f27-8803-f7e8a3da1f37.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351792767/edccd5ce-46df-42e7-a71a-760342d91884.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351816305/611a1231-2798-42de-bfed-dafc325d3e20.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351822039/5864a7a5-c34c-4d57-ae06-8d6ae57ca2c0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351827036/2201d89a-b4e4-43fc-8c71-0ddd71c7705f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351832165/95df5b0d-b43e-4fc5-8e80-778fb509aba9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351836432/3300abaa-90f6-4a45-ae6b-e8668fd4ed78.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351840478/a163e91a-0978-4460-806c-578c82f0948c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351859646/0ad2c2f8-2add-4c41-8d56-723a330a2036.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351873338/f1b3b4ed-5cd4-44f1-920a-a8a40e93f277.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351878604/fbf602f6-e2a7-425e-96aa-3ea795ccebd5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351883305/0cacc84f-8bef-4271-805c-10b3f7de25a0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351888996/19b99a08-2151-4777-9492-2a57f0efe75c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351895244/dc416ee4-d4bb-48bc-b8be-6c1275a03eaf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351898972/4ea392b6-6aa0-482a-9cc4-18f5c4a84884.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351902028/200a0e1b-d63e-4f19-a382-86b174a12302.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351905112/578f3a4d-f799-4883-89dd-2ad4e25caf9e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351910216/f81821e2-19a8-4531-a840-15b80f83620f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351913080/0cf50f00-c462-43bf-b0f0-b7cc04a9cd10.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351930163/5132fc2d-89bf-4a38-ab7d-90edfd108a6c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351934398/749d4f8e-c096-4935-847f-e011d867435f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351938756/ca06afbd-7aeb-4478-82ef-13d20da9e494.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351946477/64f66d09-3d5a-4db7-9940-71e30e166df3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351954148/0a42cfd2-0d11-4c36-8f5b-199c0327e9a3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351957495/ccaf8874-2fed-4cd7-978e-2bb2a97a7af9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351961059/30a3b0e3-0d23-4214-999b-ebd41df60737.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351967756/958906da-b93f-475d-9cb5-2b50440f29fa.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351973857/727c1904-11bc-4dda-82bb-0383a098e912.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351978456/bc3e78a0-58b7-461e-ae23-9249dd52fe0a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351981964/ae49f28a-9172-4960-8e81-5fa967988c7f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351998907/8f263a74-3ed4-4ad6-941e-962e0f248f7d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352004377/b83fea41-3598-4814-9684-209caf4500f6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352007747/ab336931-52ce-4727-afb8-2f093e226a78.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352014206/45d4651b-2a4d-41c2-9090-d5f61e4e04ab.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352020882/c7c05d45-c9e9-42f9-88f5-46a4e7785595.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352028092/244a37ce-d1c0-4b13-9d8e-f6858258a537.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352057472/b2799f37-a4f4-4b34-a5df-ae041cf7a8d1.png align="center")