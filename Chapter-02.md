# Chapter 2: Distributed Scalable 5G with Observability

## Abstract

Telecommunication, Media, and Entertainment (TME) solutions are designed for high availability, accuracy, low latency, and regulatory compliance. These solutions traditionally include operational support systems (OSS) and business support systems (BSS) to monitor and manage network performance and business workflows. The complexity of modern 5G Core platforms, combined with the need for scalability and efficient traffic management, necessitates advanced observability and traffic steering solutions.

## Introduction

In traditional hyperscaler infrastructure, regions are divided into availability zones with distributed compute, network, and storage services. However, variations in availability and cost among hyperscalers can limit workload portability. To address this, we base our solution blueprint on infrastructure-agnostic platform components such as Red Hat OpenShift, Red Hat Advanced Cluster Management, and Red Hat OpenShift Service Mesh.

## Solution Overview

3GPP standards envision a distributed 5G core with user plane function (UPF) placement based on user location. Our testbed setup includes a central SMF accessing multiple UPFs across different clusters and locations. This setup ensures that the right UPF instance is selected based on variables like DNN, TAC, and cell ID.

## Service Mesh Federation

Service mesh federation allows sharing services and workloads between separate meshes managed in distinct administrative domains. This approach ensures that communication between meshes is explicitly opt-in, aligning with the principle of least privilege. Our implementation involves configuring ingress and egress gateways for each service mesh, specifying trust domains, and declaring exported and imported services for federation.

## Observability with Submariner and L7 Mesh Connectivity

Submariner enables direct networking between Pods and Services across Kubernetes clusters, simplifying network configuration and enhancing observability. Additionally, advanced observability solutions like NetObserv Operator and Red Hat Advanced Cluster Security provide centralized monitoring and actionable insights for multi-cluster 5G deployments.

## Implementation Details

1. **Service Mesh Peering Architecture for 5G**: Involves configuring the ServiceMeshControlPlane on each service mesh to create ingress and egress gateways, specifying trust domains, and declaring exported and imported services for federation. This architecture supports seamless integration and communication between multiple service meshes, ensuring efficient management of 5G core functions across distributed locations.

2. **Network Observability and Management**: Leveraging tools like Submariner and NetObserv Operator enables real-time monitoring and management of network traffic across different clusters. This setup provides visibility into traffic patterns, performance metrics, and potential issues, allowing for proactive management and optimization of network resources.

## Challenges and Solutions

- **Scalability**: Ensuring that the 5G core can scale efficiently across multiple locations requires robust automation and management tools. By integrating solutions like Red Hat Advanced Cluster Management and leveraging GitOps practices, operators can achieve consistent and scalable deployments.
- **Security**: Protecting network traffic and ensuring secure communication between distributed components is critical. Implementing security measures such as encryption, access controls, and continuous monitoring helps safeguard the network.
- **Performance Optimization**: Achieving optimal performance in a distributed 5G core involves balancing load across different clusters and minimizing latency. Techniques such as traffic steering, load balancing, and intelligent routing are essential for maintaining high performance.

## Case Study: Implementation at a Major Telecom Provider

A major telecom provider implemented a distributed 5G core using the described architecture. By leveraging service mesh federation and Submariner for network connectivity, the provider achieved seamless integration and efficient management of 5G core functions across multiple locations. The implementation resulted in improved scalability, enhanced observability, and optimized performance, ensuring a high-quality user experience.

## Conclusion

The integration of advanced observability and traffic management solutions is essential for the successful deployment and operation of distributed 5G core networks. By leveraging technologies like service mesh federation, Submariner, and NetObserv Operator, telecom operators can achieve efficient management, enhanced security, and optimized performance in their 5G deployments. This chapter has provided an in-depth look at the architecture, implementation details, and real-world applications of these technologies, setting the stage for further exploration in subsequent chapters.