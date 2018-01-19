---
UID: NF:winsplp.RemovePrintDeviceObject
title: RemovePrintDeviceObject function
author: windows-driver-content
description: The RemovePrintDeviceObject function removes a device object from a print provider queue.
old-location: print\removeprintdeviceobject.htm
old-project: print
ms.assetid: D94A669E-4293-4235-8BC4-C7883BB0C83C
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RemovePrintDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winspool.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemovePrintDeviceObject
req.alt-loc: WinSpool.drv
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WinSpool.lib
req.dll: WinSpool.drv
req.irql: 
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# RemovePrintDeviceObject function



## -description

## -syntax

````
HRESULT WINAPI RemovePrintDeviceObject(
  _In_ HANDLE hDeviceObject
);
````


## -parameters

### -param hDeviceObject [in]

The HANDLE to the device object to be removed. This should be a device object that was  created with <a href="..\winsplp\nf-winsplp-addprintdeviceobject.md">AddPrintDeviceObject</a>.


## -returns
The <b>RemovePrintDeviceObject</b> function returns S_OK, if the device object was removed successfully. Otherwise it returns an error. 

For example, this function can return HRESULT_FROM_WIN32(ERROR_INVALID_HANDLE), if an invalid device object handle was used to call the function. And note that, regardless of the return value, the device object HANDLE becomes invalid after a call to <b>RemovePrintDeviceObject</b> has completed.


## -remarks
Call <b>RemovePrintDeviceObject</b> to remove the device object for a printer that has been deleted. When the spooler services stops, all the device objects are automatically deleted, so it is not required to call <b>RemovePrintDeviceObject</b> for each printer device object.


## -see-also
<dl>
<dt>
<a href="..\winsplp\nf-winsplp-addprintdeviceobject.md">AddPrintDeviceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20RemovePrintDeviceObject function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

