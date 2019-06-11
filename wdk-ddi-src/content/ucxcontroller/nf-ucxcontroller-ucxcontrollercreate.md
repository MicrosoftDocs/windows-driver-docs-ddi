---
UID: NF:ucxcontroller.UcxControllerCreate
title: UcxControllerCreate function (ucxcontroller.h)
description: Creates a host controller object.
old-location: buses\_ucxcontrollercreate.htm
tech.root: usbref
ms.assetid: 29A1697E-CC42-468B-B97A-A8182DA13EE9
ms.date: 05/07/2018
ms.keywords: UcxControllerCreate, UcxControllerCreate method [Buses], buses._ucxcontrollercreate, ucxcontroller/UcxControllerCreate
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucxcontroller.h
api_name:
- UcxControllerCreate
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# UcxControllerCreate function


## -description


Creates a host controller object.


## -parameters




### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.


### -param Config [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a> structure that the client driver initialized by calling UCX_CONTROLLER_CONFIG_INIT. The structure contains configuration
        information required to create the object.


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the controller object. 


### -param Controller [out]

A pointer to a variable that receives a handle to the new controller object.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the host controller must call this method after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> call. The parent of the new host controller object is the framework device object. 

During this call, the client driver-supplied event callback implementations are also registered. Supply function  pointers to those functions by call setting appropriate members of <a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a>. 

If the parent type is PCI, then initialize the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a> by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188059">UCX_CONTROLLER_CONFIG_SET_PCI_INFO</a>. If the parent is ACPI, call <a href="https://msdn.microsoft.com/library/windows/hardware/mt188058">UCX_CONTROLLER_CONFIG_SET_ACPI_INFO</a> instead. 

The method creates various queues required to handle IOCTL requests sent to the USB device. 

The method registers a device interface GUID_DEVINTERFACE_USB_HOST_CONTROLLER and symbolic link so that user mode components can open a handle to the controller.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
    WDF_OBJECT_ATTRIBUTES                   objectAttributes;
    UCX_CONTROLLER_CONFIG                   ucxControllerConfig;
    UCXCONTROLLER                           ucxController;
    PUCX_CONTROLLER_CONTEXT                 ucxControllerContext;

    // Create the controller
    //
    UCX_CONTROLLER_CONFIG_INIT(&ucxControllerConfig, "");
    ucxControllerConfig.EvtControllerUsbDeviceAdd = UsbDevice_EvtControllerUsbDeviceAdd;
    ucxControllerConfig.EvtControllerQueryUsbCapability = Controller_EvtControllerQueryUsbCapability;
    ucxControllerConfig.EvtControllerReset = Controller_EvtControllerReset;
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&objectAttributes, UCX_CONTROLLER_CONTEXT);
    
    status = UcxControllerCreate(wdfDevice,
        &ucxControllerConfig,
        &objectAttributes,
        &ucxController);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Controller, "UcxControllerCreate Failed %!STATUS!", status);
        goto Controller_WdfEvtDeviceAddEnd;
    }

    DbgTrace(TL_INFO, Controller, "UCX Controller created.");

    controllerContext-&gt;UcxController = ucxController;

    ucxControllerContext = GetUcxControllerContext(ucxController);
    ucxControllerContext-&gt;WdfDevice = wdfDevice;
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>
 

 

