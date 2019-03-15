---
UID: NC:sercx.EVT_SERCX2_APPLY_CONFIG
title: EVT_SERCX2_APPLY_CONFIG (sercx.h)
description: The EvtSerCx2ApplyConfig event callback function is called by version 2 of the serial framework extension (SerCx2) to supply the serial controller driver with a list of device-specific configuration settings to apply to the serial controller hardware.
old-location: serports\evtsercx2applyconfig.htm
tech.root: serports
ms.assetid: 8D9BC698-1E62-4DC2-B233-37022F330F98
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2ApplyConfig, EVT_SERCX2_APPLY_CONFIG, EVT_SERCX2_APPLY_CONFIG callback, EvtSerCx2ApplyConfig, EvtSerCx2ApplyConfig callback function [Serial Ports], serports.evtsercx2applyconfig
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2ApplyConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_APPLY_CONFIG callback function


## -description


The <i>EvtSerCx2ApplyConfig</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to supply the serial controller driver with a list of device-specific configuration settings to apply to the serial controller hardware.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>.


### -param ConnectionParameters [in]

A pointer to the connection parameters structure. This function must cast the pointer to the appropriate pointer type, parse the data structure to obtain the configuration settings, and apply these settings to the serial controller hardware. The connection parameters structure is defined by the hardware platform vendor and is opaque to both SerCx2 and the operating system. For more information, see Remarks.


## -returns



The <i>EvtSerCx2ApplyConfig</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



Your serial controller driver must implement this function. The driver registers the function in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

SerCx2 calls the <i>EvtSerCx2ApplyConfig</i> function during initialization of the serial controller to ensure that the hardware is in a valid initial state. Additionally, this function is called whenever a client sends an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406621">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a> request to the serial controller.

SerCx2 obtains the configuration parameters from the vendor-defined data field in the ACPI resource descriptor for the serial controller device. The data format that the ACPI firmware uses to store these configuration settings should be the same data format that is expected by the serial controller driver. For more information, see the description of the <i>UART serial bus connection descriptor</i> in the [ACPI 5.0 specification](https://www.uefi.org/specifications).

When a client sends an <b>IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</b> request to a serial port that is managed by SerCx2, SerCx2 calls the <i>EvtSerCx2ApplyConfig</i> function to pass the configuration parameters to the serial controller driver. After this callback returns, SerCx2 completes the request and uses the return value from the callback as the status code for the request.


#### Examples

To define an <i>EvtSerCx2ApplyConfig</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2ApplyConfig</i> callback function that is named <code>MyApplyConfig</code>, use the <b>EVT_SERCX2_APPLY_CONFIG</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_APPLY_CONFIG  MyApplyConfig;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MyApplyConfig(
    WDFDEVICE  Device,
    PVOID  ConnectionParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_APPLY_CONFIG</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_APPLY_CONFIG</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

The following code example shows a partial implementation of an <i>EvtSerCx2ApplyConfig</i> function for a UART:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
// Define the UART ACPI descriptor, plus any vendor-specific
// data that is needed by the serial controller (UART) driver.
//

#define ANYSIZE_ARRAY 1
#include &lt;pshpack1.h&gt;

//
// Common resource name descriptor
//
typedef struct _PNP_IO_DESCRIPTOR_RESOURCE_NAME {
    UCHAR ResourceIndex;
    UCHAR ResourceName[ANYSIZE_ARRAY];
} PNP_IO_DESCRIPTOR_RESOURCE_NAME, *PPNP_IO_DESCRIPTOR_RESOURCE_NAME;

//
// Bus descriptor for a UART
//
typedef struct _PNP_UART_SERIAL_BUS_DESCRIPTOR {
    PNP_SERIAL_BUS_DESCRIPTOR SerialBusDescriptor;
    ULONG BaudRate;
    USHORT RxBufferSize;
    USHORT TxBufferSize;
    UCHAR Parity;
    // Include any optional vendor data here:
    ...
    // Append the PNP_IO_DESCRIPTOR_RESOURCE_NAME here:
    ....
} PNP_UART_SERIAL_BUS_DESCRIPTOR, *PPNP_UART_SERIAL_BUS_DESCRIPTOR;

#include &lt;poppack.h&gt;

EVT_SERCX_APPLY_CONFIG MyApplyConfig;

//
// Implementation of an EvtSerCx2ApplyConfig callback function
//
_Use_decl_annotations_
VOID
  MyApplyConfig(
    WDFDEVICE Device,
    PVOID ConnectionParameters
    )
{
    NTSTATUS status = STATUS_SUCCESS; 
    PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER connection;
    PPNP_SERIAL_BUS_DESCRIPTOR descriptor;
    PPNP_UART_SERIAL_BUS_DESCRIPTOR uartDescriptor;

    if (ConnectionParameters == NULL)
    {
        status = STATUS_INVALID_PARAMETER; 
    }

    if (NT_SUCCESS(status))
    {
        connection = (PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER)ConnectionParameters;

        if (connection-&gt;PropertiesLength &lt; sizeof(PNP_SERIAL_BUS_DESCRIPTOR))
        {
            status = STATUS_INVALID_PARAMETER;
        }
    }

    if (NT_SUCCESS(status))
    {
        descriptor = (PPNP_SERIAL_BUS_DESCRIPTOR)connection-&gt;ConnectionProperties;

        if (descriptor-&gt;SerialBusType != UART_SERIAL_BUS_TYPE)
        {
            status = STATUS_INVALID_PARAMETER;
        }
    }

    if (NT_SUCCESS(status))
    {
        uartDescriptor = (PPNP_UART_SERIAL_BUS_DESCRIPTOR)connection-&gt;ConnectionProperties; 

        // Apply the platform-specific configuration settings
        // from the UART descriptor here:
        ...
    }

    return status;
}</pre>
</td>
</tr>
</table></span></div>
The pshpack1.h and poppack.h header files in the preceding code example control the structure alignment mode used by the compiler. The PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER and PPNP_SERIAL_BUS_DESCRIPTOR pointer types are pointers to <a href="https://msdn.microsoft.com/library/windows/hardware/jj938063">RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/jj938062">PNP_SERIAL_BUS_DESCRIPTOR</a> structures. For more information about the members of the <b>PNP_UART_SERIAL_BUS_DESCRIPTOR</b> structure, see Table 6-193 in the [ACPI 5.0 specification](https://www.uefi.org/specifications).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406621">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj938062">PNP_SERIAL_BUS_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj938063">RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>
 

 

