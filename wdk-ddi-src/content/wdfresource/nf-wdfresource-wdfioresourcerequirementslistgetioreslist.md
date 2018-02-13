---
UID: NF:wdfresource.WdfIoResourceRequirementsListGetIoResList
title: WdfIoResourceRequirementsListGetIoResList function
author: windows-driver-content
description: The WdfIoResourceRequirementsListGetIoResList method returns a handle to the framework resource-range-list object that represents a specified logical configuration in a specified resource requirements list.
old-location: wdf\wdfioresourcerequirementslistgetioreslist.htm
old-project: wdf
ms.assetid: b15c0ccf-0863-4415-b31f-b4217f249feb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoResourceRequirementsListGetIoResList, wdf.wdfioresourcerequirementslistgetioreslist, kmdf.wdfioresourcerequirementslistgetioreslist, DFResourceObjectRef_a90ce2a4-5690-49c8-ac63-6ccf89f4e5f3.xml, wdfresource/WdfIoResourceRequirementsListGetIoResList, PFN_WDFIORESOURCEREQUIREMENTSLISTGETIORESLIST, WdfIoResourceRequirementsListGetIoResList method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfIoResourceRequirementsListGetIoResList
product: Windows
targetos: Windows
req.typenames: "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product: Windows 10 or later.
---

# WdfIoResourceRequirementsListGetIoResList function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListGetIoResList</b> method returns a handle to the framework resource-range-list object that represents a specified <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> in a specified resource requirements list.


## -syntax


````
WDFIORESLIST WdfIoResourceRequirementsListGetIoResList(
  _In_ WDFIORESREQLIST RequirementsList,
  _In_ ULONG           Index
);
````


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param Index [in]

A zero-based value that is used as an index into the resource requirements list that <i>RequirementsList</i> specifies. 


## -returns



<b>WdfIoResourceRequirementsListGetIoResList</b> returns a handle to the framework resource-range-list object that represents the logical configuration that the <i>Index</i> parameter identifies, if the index value is valid. Otherwise, the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

The following code example searches a device's resource requirements list to find the first resource descriptor that describes an interrupt resource.

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
        reslist = WdfIoResourceRequirementsListGetIoResList(
                                          RequirementsList,
                                          i
                                          );

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
            // Stop if this descriptor is an interrupt descriptor.
            //
            if (descriptor-&gt;Type == CmResourceTypeInterrupt) {
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



<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistgetdescriptor.md">WdfIoResourceListGetDescriptor</a>



<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetcount.md">WdfIoResourceRequirementsListGetCount</a>



<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceRequirementsListGetIoResList method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

