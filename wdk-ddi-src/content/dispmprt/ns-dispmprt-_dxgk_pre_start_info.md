---
UID: NS:dispmprt._DXGK_PRE_START_INFO
title: _DXGK_PRE_START_INFO
author: windows-driver-content
description: Structure to allow very simple data to be exchanged between the OS and driver which may be required prior to start device being called and therefore cannot be queried through normal caps or adapter info DDIs.
old-location: display\dxgk_pre_start_info.htm
old-project: display
ms.assetid: 4CCDA951-A583-48C4-98D7-D278183D8893
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dispmprt/DXGK_PRE_START_INFO, DXGK_PRE_START_INFO, _DXGK_PRE_START_INFO, PDXGK_PRE_START_INFO, display.dxgk_pre_start_info, dispmprt/PDXGK_PRE_START_INFO, *PDXGK_PRE_START_INFO, DXGK_PRE_START_INFO structure [Display Devices], PDXGK_PRE_START_INFO structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	dispmprt.h
apiname: 
-	DXGK_PRE_START_INFO
product: Windows
targetos: Windows
req.typenames: *PDXGK_PRE_START_INFO, DXGK_PRE_START_INFO
---

# _DXGK_PRE_START_INFO structure


## -description


Structure to allow very simple data to be exchanged between the OS and driver which may be required prior to start device being called and therefore cannot be queried through normal caps or adapter info DDIs.


## -syntax


````
typedef struct _DXGK_PRE_START_INFO {
  union {
    struct {
      UINT ReservedIn;
    };
    UINT Input;
  };
  union {
    struct {
      UINT SupportPreserveBootDisplay  :1;
      UINT IsUEFIFrameBufferCpuAccessibleDuringStartup  :1;
      UINT ReservedOut  :30;
    };
    UINT Output;
  };
} DXGK_PRE_START_INFO, *PDXGK_PRE_START_INFO;
````


## -struct-fields




### -field ReservedIn

This value is reserved for system use.


### -field Input

The combined UINT value operated on.


### -field SupportPreserveBootDisplay

Flag which indicates support for preserving the timing and content of the firmware display mode across DxgkDdiStartDevice.


### -field IsUEFIFrameBufferCpuAccessibleDuringStartup

Indicates that the driver can maintain same CPU virtual address mapping to the UEFI frame buffer during driver initialization.


### -field ReservedOut

This value is reserved for system use.


### -field Output

The combined UINT value operated on.

