---
UID: NC:ursdevice.EVT_URS_SET_ROLE
title: EVT_URS_SET_ROLE (ursdevice.h)
description: The URS class extension invokes this event callback when it requires the client driver to change the role of the controller.
old-location: buses\evt_urs_set_role.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_URS_SET_ROLE callback function"]
ms.keywords: EVT_URS_SET_ROLE, EVT_URS_SET_ROLE callback, EvtUrsSetRole, EvtUrsSetRole callback function [Buses], PFN_URS_SET_ROLE, PFN_URS_SET_ROLE callback function pointer [Buses], buses.evt_urs_set_role, ursdevice/EvtUrsSetRole
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_URS_SET_ROLE
 - ursdevice/EVT_URS_SET_ROLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ursdevice.h
api_name:
 - EVT_URS_SET_ROLE
---

# EVT_URS_SET_ROLE callback function


## -description

The URS class extension invokes this event callback when it requires the client driver to change the role of the controller.

## -parameters

### -param Device [in]


A handle to the framework device object that the client driver retrieved in the previous call to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

### -param Role [in]


A <a href="/windows-hardware/drivers/ddi/urstypes/ne-urstypes-_urs_role">URS_ROLE</a> type value that indicates the role to set for the controller device.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

 To register the client driver's implementation of the event callback the driver must set the  <b>EvtUrsSetRole</b> member of <a href="/windows-hardware/drivers/ddi/ursdevice/ns-ursdevice-_urs_config">URS_CONFIG</a> to a function pointer of the implementation method and then call the <a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a> method by passing the populated structure. The driver must call the method after it creates the framework device object for the controller. 


#### Examples


```


NTSTATUS
EvtUrsSetRole (
    _In_ WDFDEVICE Device,
    _In_ URS_ROLE Role
    )
{
    NTSTATUS status;
    PFDO_CONTEXT fdoContext;

    TRACE_FUNC_ENTRY(TRACE_FLAG);
    TRY {


           // Change the current role of the controller to the specified role.
           // The driver might have stored the control registers in the device context. 
           // Read and write the register to get and set the current role. 

        }


        TRACE_INFO(TRACE_FLAG, "[Device: 0x%p] Successfully set role to %!URS_ROLE!", Device, Role);

        status = STATUS_SUCCESS;

    } FINALLY {

    }

    TRACE_FUNC_EXIT(TRACE_FLAG);

    return status;
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a>

