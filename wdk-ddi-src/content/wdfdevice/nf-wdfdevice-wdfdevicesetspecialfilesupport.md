---
UID: NF:wdfdevice.WdfDeviceSetSpecialFileSupport
title: WdfDeviceSetSpecialFileSupport function
author: windows-driver-content
description: The WdfDeviceSetSpecialFileSupport method enables or disables a function driver's support for special files, for the specified device.
old-location: wdf\wdfdevicesetspecialfilesupport.htm
old-project: wdf
ms.assetid: 7648c486-181a-45c8-9c4b-e3158428046a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_c40463ef-3c26-431e-99d8-d176b0ef7ebf.xml, WdfDeviceSetSpecialFileSupport, WdfDeviceSetSpecialFileSupport method, kmdf.wdfdevicesetspecialfilesupport, wdf.wdfdevicesetspecialfilesupport, wdfdevice/WdfDeviceSetSpecialFileSupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceSetSpecialFileSupport
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceSetSpecialFileSupport function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceSetSpecialFileSupport</b> method enables or disables a function driver's support for special files, for the specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param FileType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552509">WDF_SPECIAL_FILE_TYPE</a>-typed enumerator that identifies the type of special file that the driver supports.


### -param FileTypeIsSupported [in]

Supplies a Boolean value which, if <b>TRUE</b>, enables support for the special file type and, if <b>FALSE</b>, disables support the special file type.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A function driver typically calls <b>WdfDeviceSetSpecialFileSupport</b> from within its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.

Each driver's support for special files is initially disabled until the driver calls <b>WdfDeviceSetSpecialFileSupport</b>.

For more information, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>.


#### Examples

The following code example enables support for paging, hibernation, and dump files on a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceSetSpecialFileSupport(
                               device,
                               WdfSpecialFilePaging,
                               TRUE
                               );
WdfDeviceSetSpecialFileSupport(
                               device,
                               WdfSpecialFileHibernation,
                               TRUE
                               );
WdfDeviceSetSpecialFileSupport(
                               device,
                               WdfSpecialFileDump,
                               TRUE
                               );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552509">WDF_SPECIAL_FILE_TYPE</a>
 

 

