---
UID: NF:ks.KsGetDeviceForDeviceObject
title: KsGetDeviceForDeviceObject function
author: windows-driver-content
description: The KsGetDeviceForDeviceObject function returns the AVStream device structure for a given functional device object.
old-location: stream\ksgetdevicefordeviceobject.htm
old-project: stream
ms.assetid: 2fe72d9d-1423-4db9-be38-f2bca7dbc56d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , D, F, G, K, KsGetDeviceForDeviceObject, KsGetDeviceForDeviceObject function [Streaming Media Devices], O, avfunc_2bc27061-02ce-488f-94b4-087e9f264614.xml, b, c, e, i, j, ks/KsGetDeviceForDeviceObject, o, r, s, stream.ksgetdevicefordeviceobject, t, v"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetDeviceForDeviceObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetDeviceForDeviceObject function


## -description


The<b> KsGetDeviceForDeviceObject</b> function returns the AVStream device structure for a given functional device object.


## -syntax


````
PKSDEVICE KsGetDeviceForDeviceObject(
  _In_ PDEVICE_OBJECT FunctionalDeviceObject
);
````


## -parameters




### -param FunctionalDeviceObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> for which to return the corresponding <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure.


## -returns



<b>KsGetDeviceForDeviceObject</b> returns a pointer to the <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure corresponding to <i>FunctionalDeviceObject</i>. It returns <b>NULL</b> if <i>FunctionalDeviceObject</i> is a child PDO.




## -see-also

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\ks\nf-ks-ksgetfilterfromfileobject.md">KsGetFilterFromFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetDeviceForDeviceObject function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

