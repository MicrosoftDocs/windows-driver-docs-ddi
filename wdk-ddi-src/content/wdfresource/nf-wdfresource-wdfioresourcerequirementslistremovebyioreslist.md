---
UID: NF:wdfresource.WdfIoResourceRequirementsListRemoveByIoResList
title: WdfIoResourceRequirementsListRemoveByIoResList function
author: windows-driver-content
description: The WdfIoResourceRequirementsListRemoveByIoResList method removes a logical configuration from a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistremovebyioreslist.htm
old-project: wdf
ms.assetid: 507729e9-96da-461c-badb-a3725abf6591
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_fa50f423-3ade-4deb-89a0-d79cd3f98710.xml, WdfIoResourceRequirementsListRemoveByIoResList, WdfIoResourceRequirementsListRemoveByIoResList method, kmdf.wdfioresourcerequirementslistremovebyioreslist, wdf.wdfioresourcerequirementslistremovebyioreslist, wdfresource/WdfIoResourceRequirementsListRemoveByIoResList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
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
-	WdfIoResourceRequirementsListRemoveByIoResList
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfIoResourceRequirementsListRemoveByIoResList function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListRemoveByIoResList</b> method removes a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> from a resource requirements list.


## -syntax


````
VOID WdfIoResourceRequirementsListRemoveByIoResList(
  _In_ WDFIORESREQLIST RequirementsList,
  _In_ WDFIORESLIST    IoResList
);
````


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param IoResList [in]

A handle to a framework resource-range-list object that represents the logical configuration to be removed from the resource requirements list that <i>RequirementsList</i> specifies.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <b>WdfIoResourceRequirementsListRemoveByIoResList</b> method removes the logical configuration that is associated with the handle that the <i>IoResList</i> parameter specifies.

When <b>WdfIoResourceRequirementsListRemoveByIoResList</b> removes the logical configuration that has the index value <i>n</i>, the index value of the next logical configuration changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example searches the logical configurations in a device's resource requirements list to find a configuration that contains a specific port address. If the example finds that configuration, it removes the configuration.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Example_EvtDeviceFilterRemoveResourceRequirements(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST RequirementsList
    )
{
    ULONG i, j, reqCount, resCount;
    BOOLEAN descriptorFound = FALSE;

    //
    // Obtain the number of logical configurations.
    //
    reqCount = WdfIoResourceRequirementsListGetCount(RequirementsList);

    //
    // Search each logical configuration.
    //
    for (i = 0; i &lt; reqCount; i++) {
        WDFIORESLIST reslist;

        if (descriptorFound) {
            break;
        }
        reslist = WdfIoResourceRequirementsListGetIoResList(RequirementsList, i);

        //
        // Get the number of resource descriptors that
        // are in this logical configuration.
        //
        resCount = WdfIoResourceListGetCount(reslist);

        for (j = 0; j &lt; resCount; j++) {
            PIO_RESOURCE_DESCRIPTOR descriptor;

            //
            // Get the next resource descriptor.
            //
            descriptor = WdfIoResourceListGetDescriptor(
                                 reslist,
                                 j
                                 );

            //
            // Stop if this descriptor is the port descriptor
            // that we're looking for.
            //
            if (descriptor-&gt;Type == CmResourceTypePort) {
                if ((descriptor-&gt;u.Port.MinimumAddress) == PORT_RANGE_A) {
                    WdfIoResourceRequirementsListRemoveByIoResList(
                                 RequirementsList,
                                 reslist
                                 );
                    descriptorFound = TRUE;
                    break;
            }
        }
    }
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistgetcount.md">WdfIoResourceListGetCount</a>



<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetcount.md">WdfIoResourceRequirementsListGetCount</a>



<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistgetdescriptor.md">WdfIoResourceListGetDescriptor</a>



<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetioreslist.md">WdfIoResourceRequirementsListGetIoResList</a>



<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistremove.md">WdfIoResourceRequirementsListRemove</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceRequirementsListRemoveByIoResList method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

