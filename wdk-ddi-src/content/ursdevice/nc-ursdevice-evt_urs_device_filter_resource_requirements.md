---
UID: NC:ursdevice.EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS
title: EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS (ursdevice.h)
description: The USB dual-role class extension invokes this callback to allow the client driver to insert the resources from the resource-requirements-list object to resource lists that will be used during the life time of each role.
old-location: buses\evt_urs_device_filter_resource_requirements.htm
tech.root: usbref
ms.assetid: E5CFA6CF-1EB3-41FA-BAE4-A030737F220D
ms.date: 05/07/2018
ms.keywords: EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS, EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback, EvtUrsDeviceFilterResourceRequirements, EvtUrsDeviceFilterResourceRequirements callback function [Buses], PFN_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS, PFN_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback function pointer [Buses], buses.evt_urs_device_filter_resource_requirements, ursdevice/EvtUrsDeviceFilterResourceRequirements
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ursdevice.h
api_name:
- PFN_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS callback function


## -description


The USB dual-role class extension invokes this callback to allow the client driver to insert the resources from the resource-requirements-list object to resource lists that will be used during the life time of each role.


## -parameters




### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.


### -param IoResourceRequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param HostRoleResources [in]

A handle to a resource list for the controller device when it is operating in host mode. 


### -param FunctionRoleResources [in]

A handle to a resource list for the controller when it is operating in function mode. 


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The client driver registers its implementation with the USB dual-role class extension by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628012">UrsDeviceInitialize</a> after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> to create the framework device object for the controller. The class extension invokes this callback before <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>. The callback is invoked within the class extension's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540870">EvtDeviceFilterRemoveResourceRequirements</a>, which is registered on behalf of the client driver. The client must not implement and register its <i>EvtDeviceFilterRemoveResourceRequirements</i> because it will override the class extension's implementation.

Each role has a certain number of assigned hardware resources. Those resources can be memory, interrupts, and so on. The resources are maintained by the system in a <i>resource requirements list</i> that contains the range of hardware resources in which the device can operate. 

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Handling Hardware Resources</a>.

The class extension allocates memory for the <i>resource requirements list</i> and <i>resource lists</i> for both host and function roles. When the class extension  invokes the client driver's implementation of <i>EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</i>, it passes a WDFIORESREQLIST handle to that requirements list along with URSIORESLIST handles for host and function role <i>resource lists</i>. In the implementation, the client driver is expected to enumerate through the logical configurations in the requirements list and check the resource descriptor for each configuration by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548510">WdfIoResourceListGetDescriptor</a>. 

If the driver wants to use a particular resource, it can add the associated resource descriptor  to the respective resource list by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628016">UrsIoResourceListAppendDescriptor</a>.

To delete a resource descriptor from the requirement list, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548523">WdfIoResourceListRemove</a>. 


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtUrsFilterRemoveResourceRequirements;


_Function_class_(EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS)
_IRQL_requires_same_
_IRQL_requires_max_(PASSIVE_LEVEL)
NTSTATUS
EvtUrsFilterRemoveResourceRequirements (
    _In_ WDFDEVICE Device,
    _In_ WDFIORESREQLIST IoResourceRequirementsList,
    _In_ URSIORESLIST HostRoleResources,
    _In_ URSIORESLIST FunctionRoleResources
    )
{
    NTSTATUS status;
    WDFIORESLIST resList;
    ULONG resListCount;
    ULONG resCount;
    ULONG currentResourceIndex;
    PIO_RESOURCE_DESCRIPTOR descriptor;
    BOOLEAN assignToHost;
    BOOLEAN assignToFunction;
    BOOLEAN keepAssigned;

    TRY {

        status = STATUS_SUCCESS;

        //
        // Currently does not support multiple logical configurations. Only the first one
        // is considered.
        //

        resListCount = WdfIoResourceRequirementsListGetCount(IoResourceRequirementsList);
        if (resListCount == 0) {
            // No logical resource configurations found.
            LEAVE;
        }

        // Enumerate through logical resource configurations.

        resList = WdfIoResourceRequirementsListGetIoResList(IoResourceRequirementsList, 0);
        resCount = WdfIoResourceListGetCount(resList);


        for (currentResourceIndex = 0; currentResourceIndex &lt; resCount; ++currentResourceIndex) {

            descriptor = WdfIoResourceListGetDescriptor(resList, currentResourceIndex);

            if (descriptor-&gt;Type == CmResourceTypeConfigData) {

                //
                // This indicates the priority of this logical configuration.
                // This descriptor can be ignored.
                //

                keepAssigned = TRUE;
                assignToFunction = FALSE;
                assignToHost = FALSE;

            } else if ((descriptor-&gt;Type == CmResourceTypeMemory) ||
                       (descriptor-&gt;Type == CmResourceTypeMemoryLarge)) {

                //
                // This example client driver keeps the memory resources here. 
                //

                keepAssigned = TRUE;
                assignToFunction = TRUE;
                assignToHost = TRUE;

            } else {

                //
                // For all other resources, pass it to the child device nodes for host and function.
                //

                keepAssigned = FALSE;
                assignToHost = TRUE;
                assignToFunction = TRUE;
            }

            if (assignToHost != FALSE) {
                status = UrsIoResourceListAppendDescriptor(HostRoleResources, descriptor);
                if (!NT_SUCCESS(status)) {
                    // UrsIoResourceListAppendDescriptor for HostRoleResources failed.
                    LEAVE;
                }
            }

            if (assignToFunction != FALSE) {
                status = UrsIoResourceListAppendDescriptor(FunctionRoleResources, descriptor);
                if (!NT_SUCCESS(status)) {
                    // UrsIoResourceListAppendDescriptor for FunctionRoleResources failed.
                    LEAVE;
                }
            }

            if (keepAssigned == FALSE) {
                WdfIoResourceListRemove(resList, currentResourceIndex);
                --currentResourceIndex;
                --resCount;
            }
        }

    } FINALLY {
    }

    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Handling Hardware Resources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt628012">UrsDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt628016">UrsIoResourceListAppendDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548523">WdfIoResourceListRemove</a>
 

 

