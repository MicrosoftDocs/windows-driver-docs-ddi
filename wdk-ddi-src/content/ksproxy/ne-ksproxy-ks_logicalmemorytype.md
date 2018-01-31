---
UID: NE:ksproxy.KS_LogicalMemoryType
title: KS_LogicalMemoryType
author: windows-driver-content
description: "."
old-location: stream\ks_logicalmemorytype.htm
old-project: stream
ms.assetid: B02E5131-6407-4481-BABD-9F5BDA979D85
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_MemoryTypeDeviceSpecific, *PKS_LogicalMemoryType, stream.ks_logicalmemorytype, KS_MemoryTypeKernelNonPaged, ksproxy/KS_MemoryTypeKernelNonPaged, KS_MemoryTypeDeviceHostMapped, ksproxy/KS_LogicalMemoryType, KS_MemoryTypeUser, ksproxy/KS_MemoryTypeKernelPaged, KS_MemoryTypeKernelPaged, ksproxy/KS_MemoryTypeUser, ksproxy/KS_MemoryTypeDeviceSpecific, ksproxy/KS_MemoryTypeAnyHost, KS_LogicalMemoryType, ksproxy/KS_MemoryTypeDeviceHostMapped, KS_LogicalMemoryType enumeration [Streaming Media Devices], KS_MemoryTypeAnyHost, KS_MemoryTypeDontCare, ksproxy/KS_MemoryTypeDontCare
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksproxy.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksproxy.h
apiname:
-	KS_LogicalMemoryType
product: Windows
targetos: Windows
req.typenames: KS_LogicalMemoryType
---

# KS_LogicalMemoryType enumeration


## -description





## -syntax


````
typedef enum  { 
  KS_MemoryTypeDontCare          = 0,
  KS_MemoryTypeKernelPaged,
  KS_MemoryTypeKernelNonPaged,
  KS_MemoryTypeDeviceHostMapped,
  KS_MemoryTypeDeviceSpecific,
  KS_MemoryTypeUser,
  KS_MemoryTypeAnyHost
} KS_LogicalMemoryType;
````


## -enum-fields




#### - KS_MemoryTypeDontCare



#### - KS_MemoryTypeKernelPaged



#### - KS_MemoryTypeKernelNonPaged



#### - KS_MemoryTypeDeviceHostMapped



#### - KS_MemoryTypeDeviceSpecific



#### - KS_MemoryTypeUser



#### - KS_MemoryTypeAnyHost


