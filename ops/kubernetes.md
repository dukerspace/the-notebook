---
id: kubernetes
title: Kubernetes
type: docs
path: the-notebook/ops/kubernetes
---

## Kubernetest

[Learn online](https://www.katacoda.com/courses/kubernetes)

### ประเภท Nodes

- Worker Node : ทำหน้าที่ run application ซึ่ง Application ที่ Run บน Nodes จะทำงานอยู่ในรูปแบบของ “Container”
  Worker Nodes สามารถมีได้หลายเครื่อง เพื่อช่วยกัน แบ่งเบาภาระการทำงาน เมื่อนำหลาย ๆ เครื่องมาจัดกลุ่มรวมกัน จะเรียกว่า “Cluster”
- Master Node : ทำหน้าที่คอยควบคุมดูแล Cluster หรือ Worker Nodes ให้ทำงานตามที่ผู้ดูแลระบบสั่งการ
  Master Nodes อาจมีหลายเครื่องเพื่อช่วยกันดูแล Cluster

### Application / Kind / Resources

- Pod : คือ Application / Kind / Resources หน่วย (Unit) ที่เล็กที่สุดของ Kubernetes
  1 Pod สามารถมีได้ 1 หรือมากกว่า 1 Container แต่ส่วนใหญ่มักที่จะเป็น 1 Container
  ReplicaSet คือ ตัวคอยควบคุมจำนวนของ Pods ให้เป็นไปตามที่ได้ตั้งค่าไว้

- Deployment : Deployment = Pods + ReplicaSet
  เป็น Description / Definition file ที่เอาไว้อธิบายรายละเอียดของ Pods + ReplicaSet ว่าการ Run Application นี้ ให้สร้าง Pods ขึ้นมาจาก Docker Image ใดและให้มี Replicas (หรือ จำนวนของ Pods) เป็นเท่าใดใน Cluster

- Labels : เป็นสิ่งที่เอาไว้แปะใส่ Application/Kind/Resources แต่ละประเภท เพื่อใช้สำหรับอธิบายหรือเอาไว้ค้นหา (Search) หรือเอาไว้เลือก (Select) Object ของ Kind ต่าง ๆ จาก Labels ที่แปะ (กำหนด) ไว้
- Services : Services = Pods Load Balancer + etc.
  หน้าที่หลัก ๆ ของ Services คือ ทำหน้าที่กระจาย Load ไปยัง Pods ที่ตัวเองดูแลอยู่โดยดูจาก Pods ที่มี Label ตรงตามที่กำหนดไว้ รวมถึงทำหน้าที่ Abstract ปลายทางที่ Service นั้นกำลังเชื่อมต่อด้วย

**_การทำงานภายใน Kubernetes จะไม่ทำการเชื่อมต่อไปที่ Pods ตรง ๆ แต่จะเชื่อมต่อไปที่ Services แทน_**

### Service Types

- ClusterIP : เป็น Services ที่เอาไว้ Expose เพื่อใช้งานกันเฉพาะภายใน Cluster เท่านั้น ภายนอกไม่สามารถเข้าถึง Service Type นี้ได้ เช่น การใช้งาน Database หรือ Service ภายในที่ไม่ต้องการให้ข้างนอกเข้าถึง Service นั้น ๆ
- NodePort : เป็นการทำให้ Service ภายใน Cluster ของเราสามารถ Expose ออกไปข้างนอก Cluster ได้ ผ่าน Port ของ Node ทำให้ภายนอกสามารถเข้าถึง Service ของเราได้

  **_หมายเหตุ Port ที่สามารถกำหนดได้ของ Service Type : NodePort คือ 30,000–32,767_**

- LoadBalancer : เป็นการทำให้ Service ภายใน Cluster ของเราสามารถ Expose ออกไปข้างนอกได้ แบบ NodePort แต่ Expose ผ่าน Load Balancer ของ Cloud Provider ทำให้ภายนอกสามารถเข้าถึง Service ของเราได้

  **_Service Type นี้ใช้ได้เฉพาะ Kubernetes Service บน Cloud เท่านั้น_**

- ExternalName : เป็นการทำให้ Application ของเรา (Pods) สามารถเข้าถึง External Service ภายนอก Cluster ได้ด้วยการ Mapping External Service ให้เป็น Kubernetes Service

### Endpoints

- เป็นการทำให้ Application ของเรา (Pods) สามารถเข้าถึง External Service ภายนอก Cluster ได้ด้วยการชี้ Service ไปที่ Endpoints ของ External Service

### Ingress

- Ingress = Reverse Proxy
- Ingress Controller
  - Nginx Ingress Controller
  - HAProxy Ingress
  - Kong Ingress Controller
  - AWS ALB Ingress Controller
  - AKS Application Gateway Ingress Controller
  - etc.

### Namespace

- เป็นการจัดกลุ่มของ Resources ต่าง ๆ เช่น Pods, ReplicaSet,Deployment, Services, Ingress, etc. ให้อยู่ในกลุ่ม (Namespace) เดียวกัน

### ConfigMap

- เป็นการกำหนด Configuration ที่เราต้องการ ให้อยู่ในรูปแบบของ Configuration บน Kebernetes เพื่อให้ Resources ต่าง ๆ สามารถอ่านค่า Configuration นี้ไปใช้ได้

### Secret

- เป็นการจัดเก็บ Configuration แบบที่ต้องการเก็บเป็นความลับ ที่เราต้องการ ให้อยู่ในรูปแบบของ Secret บน Kebernetes เพื่อให้ Resources ต่าง ๆ สามารถอ่านค่า Secret นี้ไปใช้ได้ เช่น Username/Password หรือ Token ที่ใช้ในการเข้าถึง External Resources ต่าง ๆ

---

## kubectl

### create

- kubectl create -f <file.yml>

```
kubectl create -f hello.yml
```

### delete

- kubectl delete -f <file.yml>

```kubectl delete -f hello.yml

```

### get

- kubectl get pods
