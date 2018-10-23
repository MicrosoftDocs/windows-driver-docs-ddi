---
UID: NS:sercx._SERCX_CONFIG
title: "_SERCX_CONFIG"
author: windows-driver-content
description: The SERCX_CONFIG structure contains configuration information for the serial framework extension (SerCx).
old-location: serports\sercx_config.htm
tech.root: serports
ms.assetid: 2CBCBA07-C489-4475-A856-8748FBFDC141
ms.date: 04/23/2018
ms.keywords: "*PSERCX_CONFIG, 1/PSERCX_CONFIG, 1/SERCX_CONFIG, PSERCX_CONFIG, PSERCX_CONFIG structure pointer [Serial Ports], SERCX_CONFIG, SERCX_CONFIG structure [Serial Ports], _SERCX_CONFIG, serports.sercx_config"
ms.topic: struct
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1.0\Sercx.h
api_name:
-	SERCX_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SERCX_CONFIG, *PSERCX_CONFIG
---

# _SERCX_CONFIG structure


## -description


The <b>SERCX_CONFIG</b> structure contains configuration information for the serial framework extension (SerCx).


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field PowerManaged

Whether the controller queue should be power-managed. If set to <b>WdfTrue</b>, the controller queue should be power-managed.  If set to <b>WdfFalse</b>, the controller queue not be power-managed. If set to <b>WdfDefault</b>, the controller queue should be power-managed unless the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547273">WdfFdoInitSetFilter</a> method. For more information, see the description of the <b>PowerManaged</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a>.


### -field EvtSerCxFileOpen

A pointer to the controller driver's <a href="https://msdn.microsoft.com/90D08857-69E0-4DD9-9588-86900466E8DE">EvtSerCxFileOpen</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxFileClose

A pointer to the controller driver's <a href="https://msdn.microsoft.com/C72CA6D0-DD85-46AC-9CE3-BE11233475C0">EvtSerCxFileClose</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxFileCleanup

A pointer to the controller driver's <a href="https://msdn.microsoft.com/D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC">EvtSerCxFileCleanup</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxTransmit

A pointer to the controller driver's <a href="https://msdn.microsoft.com/B32335E4-3BDF-4161-9BE2-CF3557D76988">EvtSerCxTransmit</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxReceive

A pointer to the controller driver's <a href="https://msdn.microsoft.com/C862D632-5425-4EEB-9C5D-BC3721D9F132">EvtSerCxReceive</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxWaitmask

A pointer to the controller driver's <a href="https://msdn.microsoft.com/41F60807-5A00-4B0E-A57D-70D25C73F575">EvtSerCxWaitmask</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxPurge

A pointer to the controller driver's <a href="https://msdn.microsoft.com/036D9AAC-C740-4108-B952-0A4F91585488">EvtSerCxPurge</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxControl

A pointer to the controller driver's <a href="https://msdn.microsoft.com/2A88BA68-48A7-4C00-8031-CCC50A0C090D">EvtSerCxControl</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxApplyConfig

A pointer to the controller driver's <a href="https://msdn.microsoft.com/DC0AB4E3-AA73-4DD5-B91D-95F9D3792321">EvtSerCxApplyConfig</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxTransmitCancel

A pointer to the controller driver's <a href="https://msdn.microsoft.com/7922A3BD-8829-42A3-9F94-3C26F1262626">EvtSerCxTransmitCancel</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxReceiveCancel

A pointer to the controller driver's <a href="https://msdn.microsoft.com/17362701-67C9-4275-B072-CB17111A838F">EvtSerCxReceiveCancel</a> callback function. This member is optional and can be set to NULL.


## -remarks



Before this structure is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method, it must be initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439553">SERCX_CONFIG_INIT</a> function, and then modified by the controller driver to set the callback function pointers and the <b>PowerManaged</b> member.




## -see-also




<a href="https://msdn.microsoft.com/DC0AB4E3-AA73-4DD5-B91D-95F9D3792321">EvtSerCxApplyConfig</a>



<a href="https://msdn.microsoft.com/2A88BA68-48A7-4C00-8031-CCC50A0C090D">EvtSerCxControl</a>



<a href="https://msdn.microsoft.com/D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC">EvtSerCxFileCleanup</a>



<a href="https://msdn.microsoft.com/C72CA6D0-DD85-46AC-9CE3-BE11233475C0">EvtSerCxFileClose</a>



<a href="https://msdn.microsoft.com/90D08857-69E0-4DD9-9588-86900466E8DE">EvtSerCxFileOpen</a>



<a href="https://msdn.microsoft.com/036D9AAC-C740-4108-B952-0A4F91585488">EvtSerCxPurge</a>



<a href="https://msdn.microsoft.com/C862D632-5425-4EEB-9C5D-BC3721D9F132">EvtSerCxReceive</a>



<a href="https://msdn.microsoft.com/17362701-67C9-4275-B072-CB17111A838F">EvtSerCxReceiveCancel</a>



<a href="https://msdn.microsoft.com/B32335E4-3BDF-4161-9BE2-CF3557D76988">EvtSerCxTransmit</a>



<a href="https://msdn.microsoft.com/7922A3BD-8829-42A3-9F94-3C26F1262626">EvtSerCxTransmitCancel</a>



<a href="https://msdn.microsoft.com/41F60807-5A00-4B0E-A57D-70D25C73F575">EvtSerCxWaitmask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439553">SERCX_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547273">WdfFdoInitSetFilter</a>
 

 

