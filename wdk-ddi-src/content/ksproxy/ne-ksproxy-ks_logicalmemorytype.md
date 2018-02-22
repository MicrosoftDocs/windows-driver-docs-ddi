---
UID: NE:ksproxy.KS_LogicalMemoryType
title: KS_LogicalMemoryType
author: windows-driver-content
description: "."
old-location: stream\ks_logicalmemorytype.htm
old-project: stream
ms.assetid: B02E5131-6407-4481-BABD-9F5BDA979D85
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KS_MemoryTypeUser, ksproxy/KS_MemoryTypeAnyHost, KS_MemoryTypeDeviceHostMapped, KS_MemoryTypeKernelNonPaged, ksproxy/KS_MemoryTypeKernelNonPaged, KS_LogicalMemoryType enumeration [Streaming Media Devices], ksproxy/KS_MemoryTypeDeviceSpecific, *PKS_LogicalMemoryType, ksproxy/KS_MemoryTypeDontCare, stream.ks_logicalmemorytype, KS_MemoryTypeDeviceSpecific, ksproxy/KS_LogicalMemoryType, KS_MemoryTypeDontCare, ksproxy/KS_MemoryTypeKernelPaged, ksproxy/KS_MemoryTypeDeviceHostMapped, KS_MemoryTypeAnyHost, KS_MemoryTypeKernelPaged, KS_LogicalMemoryType, ksproxy/KS_MemoryTypeUser
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




### -field KS_MemoryTypeDontCare


### -field KS_MemoryTypeKernelPaged


### -field KS_MemoryTypeKernelNonPaged


### -field KS_MemoryTypeDeviceHostMapped


### -field KS_MemoryTypeDeviceSpecific


### -field KS_MemoryTypeUser


### -field KS_MemoryTypeAnyHost

