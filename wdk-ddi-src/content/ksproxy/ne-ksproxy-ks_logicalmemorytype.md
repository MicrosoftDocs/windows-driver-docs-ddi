---
UID: NE:ksproxy.KS_LogicalMemoryType
title: KS_LogicalMemoryType
author: windows-driver-content
description: .
old-location: stream\ks_logicalmemorytype.htm
old-project: stream
ms.assetid: B02E5131-6407-4481-BABD-9F5BDA979D85
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_LogicalMemoryType, KS_LogicalMemoryType, *PKS_LogicalMemoryType
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
req.alt-api: KS_LogicalMemoryType
req.alt-loc: Ksproxy.h
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


## -remarks
