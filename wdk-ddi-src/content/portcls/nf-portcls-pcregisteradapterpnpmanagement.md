---
UID: NF:portcls.PcRegisterAdapterPnpManagement
title: PcRegisterAdapterPnpManagement function
author: windows-driver-content
description: The PcRegisterAdapterPnpManagement function registers the adapter's PnP-management interface with the PortCls system driver. It is used to support PnP rebalance.
old-location: audio\pcregisteradapterpnpmanagement.htm
old-project: audio
ms.assetid: DF597216-FB81-466C-871E-5E08C69B78DA
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: PcRegisterAdapterPnPManagement function [Audio Devices], PcRegisterAdapterPnpManagement, portcls/PcRegisterAdapterPnPManagement, audio.pcregisteradapterpnpmanagement, PcRegisterAdapterPnPManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
-	PcRegisterAdapterPnPManagement
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# PcRegisterAdapterPnpManagement function


## -description


The  PcRegisterAdapterPnpManagement function registers the adapter's PnP-management interface with the PortCls system driver.  It is used to support PnP rebalance. 


## -syntax


````
NTSTATUS PcRegisterAdapterPnPManagement(
  _In_ PUNKNOWN       pUnknown,
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param Unknown

TBD


### -param DeviceObject [in]

Specifies a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


#### - pUnknown [in]

Pointer to an adapter driver object's <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. The PortCls system driver queries this object for its <a href="..\portcls\nn-portcls-iadapterpnpmanagement.md">IAdapterPnpManagement</a> interface.


## -returns



<b>PcRegisterAdapterPnpManagement</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



Portcls uses <b>PcRegisterAdapterPnpManagement</b> and <a href="..\portcls\nf-portcls-pcunregisteradapterpnpmanagement.md">PcUnregisterAdapterPnpManagement</a> to support PNP rebalance.

For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.




## -see-also

<a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>



<a href="..\portcls\nf-portcls-pcunregisteradapterpnpmanagement.md">PcUnregisterAdapterPnpManagement</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\portcls\nn-portcls-iadapterpnpmanagement.md">IAdapterPnpManagement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterAdapterPnpManagement function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

