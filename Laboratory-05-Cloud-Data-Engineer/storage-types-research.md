# Cloud Storage Types Comparison

| Storage Type   | Description | Primary Use Case | Cloud Provider Example |
|----------------|-------------|-------------------|--------------------------|
| Block Storage  | Splits data into fixed-size blocks, each with a unique address, and attaches directly to a single virtual machine like a raw hard disk. | Databases, OS boot volumes, and applications that need low-latency random read/write access. | AWS EBS |
| File Storage   | Organizes data in a hierarchical folder/file structure, accessed over a network protocol (e.g., NFS/SMB) and shareable across multiple machines at once. | Shared drives, content management systems, home directories. | AWS EFS |
| Object Storage | Stores data as discrete objects (data + metadata + a unique identifier) in a flat namespace, accessed via HTTP-based APIs rather than a file system. | Storing massive amounts of unstructured data at scale — images, video, backups, static web assets. | AWS S3 |

## Why Object Storage is Best for Client Photos

Object storage is the ideal choice for storing the client's user-uploaded images because it scales virtually without limit and doesn't require the rigid capacity planning that block storage demands. Each photo is stored as an independent object with its own metadata and unique URL, making it simple to retrieve, distribute, and serve directly to web or mobile clients over HTTP. This also avoids the problem of storing files inside ephemeral web server containers, since the storage lives on a separate, durable, purpose-built service.
