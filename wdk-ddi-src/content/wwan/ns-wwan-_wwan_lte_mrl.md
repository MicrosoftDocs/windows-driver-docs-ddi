---
UID: NS:wwan._WWAN_LTE_MRL
title: _WWAN_LTE_MRL (wwan.h)
description: The WWAN_LTE_MRL structure represents the measured results list (MRL) of neighboring LTE cells.
old-location: netvista\wwan_lte_mrl.htm
tech.root: netvista
ms.assetid: 5959B7A7-147D-4F20-82CC-EC1DEAAE3494
ms.date: 05/02/2018
ms.keywords: "*PWWAN_LTE_MRL, PWWAN_LTE_MRL, PWWAN_LTE_MRL structure pointer [Network Drivers Starting with Windows Vista], WWAN_LTE_MRL, WWAN_LTE_MRL structure [Network Drivers Starting with Windows Vista], _WWAN_LTE_MRL, netvista.wwan_lte_mrl, wwan/PWWAN_LTE_MRL, wwan/WWAN_LTE_MRL"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_LTE_MRL
product:
- Windows
targetos: Windows
req.typenames: WWAN_LTE_MRL, *PWWAN_LTE_MRL
---

# _WWAN_LTE_MRL structure


## -description


The <b>WWAN_LTE_MRL</b> structure represents the measured results list (MRL) of neighboring LTE cells.


## -struct-fields




### -field ElementCount

The count of MRL entries following this member.


### -field LTEMrl

The array of MRL records, each specified as a <a href="https://msdn.microsoft.com/49C3D862-EB78-4C44-A7B7-CE15E79EB021">WWAN_LTE_MRL_INFO</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://msdn.microsoft.com/66460B28-C2B4-4F05-A133-31A753AF9489">WWAN_BASE_STATIONS_INFO</a>



<a href="https://msdn.microsoft.com/49C3D862-EB78-4C44-A7B7-CE15E79EB021">WWAN_LTE_MRL_INFO</a>



<a href="https://msdn.microsoft.com/17A78DC7-A89D-405A-983E-FC0DC469A4B0">WWAN_LTE_SERVING_CELL_INFO</a>
 

 

