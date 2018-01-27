---
UID: NF:portcls.PcRegisterAdapterPowerManagement
title: PcRegisterAdapterPowerManagement function
author: windows-driver-content
description: The PcRegisterAdapterPowerManagement function registers the adapter's power-management interface with the PortCls system driver.
old-location: audio\pcregisteradapterpowermanagement.htm
old-project: audio
ms.assetid: a9e2537d-4d67-4495-b391-55f885b7041a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcRegisterAdapterPowerManagement function [Audio Devices], PcRegisterAdapterPowerManagement, portcls/PcRegisterAdapterPowerManagement, audio.pcregisteradapterpowermanagement, audpc-routines_524bed01-a6ba-492c-9e18-7495de15be46.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows 2000.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Portcls.lib
-	Portcls.dll
apiname: 
-	PcRegisterAdapterPowerManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcRegisterAdapterPowerManagement function


## -description


The <b>PcRegisterAdapterPowerManagement</b> function registers the adapter's power-management interface with the PortCls system driver.


## -syntax


````
NTSTATUS PcRegisterAdapterPowerManagement(
  _In_ PUNKNOWN pUnknown,
  _In_ PVOID    pvContext1
);
````


## -parameters




### -param Unknown

TBD


### -param pvContext1 [in]

Pointer to the adapter's <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">functional device object (FDO)</a>. This parameter is a pointer to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> but is cast to type PVOID.


#### - pUnknown [in]

Pointer to an adapter driver object's <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. The PortCls system driver queries this object for its <a href="..\portcls\nn-portcls-iadapterpowermanagement.md">IAdapterPowerManagement</a> interface.


## -returns


<b>PcRegisterAdapterPowerManagement</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\portcls\nn-portcls-iadapterpowermanagement.md">IAdapterPowerManagement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterAdapterPowerManagement function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

