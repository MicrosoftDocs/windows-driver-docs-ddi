---
UID: NC:srb.PHW_ADAPTER_CONTROL
title: PHW_ADAPTER_CONTROL
author: windows-driver-content
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_adapter_control.htm
old-project: storage
ms.assetid: ef58c005-e5e5-409d-9010-59635fd4da02
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.phw_adapter_control, (*PHW_ADAPTER_CONTROL) callback function [Storage Devices], (*PHW_ADAPTER_CONTROL), srb/(*PHW_ADAPTER_CONTROL), ide_minikr_fb5a2e9f-b755-417e-b152-ef680c85c16a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
req.target-type: Desktop
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	srb.h
apiname:
-	(*PHW_ADAPTER_CONTROL)
product: Windows
targetos: Windows
req.typenames: "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product: Windows 10 or later.
---

# PHW_ADAPTER_CONTROL callback


## -description


The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs. 


## -prototype


````
typedef SCSI_ADAPTER_CONTROL_STATUS (*PHW_ADAPTER_CONTROL)(
  _In_ PVOID                     DeviceExtension ,
  _In_ SCSI_ADAPTER_CONTROL_TYPE ControlType ,
  _In_ PVOID                     Parameters
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area. 


### -param ControlType [in]

Specifies an adapter-control operation. For a list of the allowed operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>. 


### -param Parameters [in]

Contains information related to the <i>ControlType</i>. For an explanation of the meaning of these values, see the discussion accompanying the <i>Parameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>.   


## -returns


The routine declared by this prototype returns different sets of values depending on the control type. For a complete description of the return values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>. 



## -remarks


The adapter control routine for both SCSI and StorPort miniport drivers are declared using this prototype. 

For more information about the SCSI miniport driver's adapter control routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>. 

For more information about the adapter control routine that is used with the StorPort driver's miniport driver, see <a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>

<a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_ADAPTER_CONTROL callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

