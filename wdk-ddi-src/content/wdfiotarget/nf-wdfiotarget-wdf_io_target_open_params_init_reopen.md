---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function (wdfiotarget.h)
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can reopen a remote I/O target.
old-location: wdf\wdf_io_target_open_params_init_reopen.htm
tech.root: wdf
ms.assetid: 00f1e870-4c74-44d3-9ee9-c8b9e63e5f3b
ms.date: 02/26/2018
keywords: ["WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function"]
ms.keywords: DFIOTargetRef_f0c123bb-3ecc-401f-ad91-4ed1b359454d.xml, WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN, WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function, kmdf.wdf_io_target_open_params_init_reopen, wdf.wdf_io_target_open_params_init_reopen, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
f1_keywords:
 - "wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN"
 - "WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfiotarget.h
api_name:
- WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
targetos: Windows
req.typenames: 
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can reopen a remote I/O target. 


## -parameters




### -param Params 
[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> method. Your driver should call <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> to initialize a <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure if the driver is calling <b>WdfIoTargetOpen</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a> callback function.

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure and sets the structure's <b>Size</b> member. Then, the function sets the <b>Type</b> member to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WdfIoTargetOpenReopen</a>.

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example is a segment of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a> callback function that reopens a remote I/O target.

```cpp
VOID
MyEvtIoTargetRemoveCanceled(
    WDFIOTARGET IoTarget
    )
{
    WDF_IO_TARGET_OPEN_PARAMS openParams;
    NTSTATUS status;

...
    WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN(&openParams);
    status = WdfIoTargetOpen(
                             IoTarget,
                             &openParams
                             );
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WdfIoTargetOpenReopen</a>
 

 

