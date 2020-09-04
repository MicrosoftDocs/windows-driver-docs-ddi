---
UID: NC:sercx.EVT_SERCX_APPLY_CONFIG
title: EVT_SERCX_APPLY_CONFIG (sercx.h)
description: The EvtSerCxApplyConfig event callback function instructs the serial controller driver to apply a list of configuration settings to the serial controller hardware.
old-location: serports\evtsercxapplyconfig.htm
tech.root: serports
ms.assetid: DC0AB4E3-AA73-4DD5-B91D-95F9D3792321
ms.date: 04/23/2018
keywords: ["EVT_SERCX_APPLY_CONFIG callback function"]
ms.keywords: 1/EvtSerCxApplyConfig, EVT_SERCX_APPLY_CONFIG, EVT_SERCX_APPLY_CONFIG callback, EvtSerCxApplyConfig, EvtSerCxApplyConfig callback function [Serial Ports], serports.evtsercxapplyconfig
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX_APPLY_CONFIG
 - sercx/EVT_SERCX_APPLY_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 1.0\Sercx.h
api_name:
 - EvtSerCxApplyConfig
---

# EVT_SERCX_APPLY_CONFIG callback function


## -description

The <i>EvtSerCxApplyConfig</i> event callback function instructs the serial controller driver to apply a list of configuration settings to the serial controller hardware.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller.

### -param ConnectionParameters 

[in]
A pointer to the connection parameters structure.  This function must cast this parameter to the appropriate pointer type, parse the data structure to obtain the configuration settings, and apply these settings to the serial controller hardware. The connection parameters structure is defined by the hardware platform vendor and is opaque to both the serial framework extension (SerCx) and the operating system.

## -returns

The <i>EvtSerCxApplyConfig</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## -remarks

SerCx calls this function during initialization of the serial controller to ensure that the hardware is in a valid initial state. Additionally, this function is called whenever a client sends an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_apply_default_configuration">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a> I/O control request to the controller.

SerCx obtains these configuration parameters from the ACPI resource descriptor for the serial controller device. The data format that the ACPI firmware uses to store these configuration settings should be the same data format that is expected by the serial controller driver.

When a client sends an <b>IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</b> request to a serial port that is managed by SerCx, SerCx determines whether the serial controller driver for the serial port supports the <i>EvtSerCxApplyConfig</i> callback, and whether the ACPI resource descriptor for the serial port provides default connection settings. If not, SerCx completes the request with error status code STATUS_NOT_SUPPORTED. Otherwise, SerCx passes the connection parameters to the driver's <i>EvtSerCxApplyConfig</i> callback function. After this callback returns, SerCx completes the request and uses the return value from the callback as the status code for the request.

If a serial controller driver needs to obtain the default connection parameters at a time other than during an <i>EvtSerCxApplyConfig</i> callback, the driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxgetconnectionparameters">SerCxGetConnectionParameters</a> method.

To register an <i>EvtSerCxApplyConfig</i> callback function, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  EVT_SERCX_APPLY_CONFIG(
    __in WDFDEVICE Device
    );
```

To define an <i>EvtSerCxApplyConfig</i> callback function that is named <code>MyEvtSerCxApplyConfig</code>, you must first provide a function declaration that <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_APPLY_CONFIG MyEvtSerCxApplyConfig;
```

Then, implement your callback function as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
  MyEvtSerCxApplyConfig(
    __in WDFDEVICE Device
    )
{ ... }
```

For more information about SDV requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>
The following code example shows a partial implementation of an <i>EvtSerCxApplyConfig</i> function for a UART.

<div class="code"><span codelanguage="cpp"><table>
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

EVT_SERCX_APPLY_CONFIG UartEvtApplyConfig;

//
// Implementation of an EvtSerCxApplyConfig callback function
//
NTSTATUS
  UartEvtApplyConfig(
    __in WDFDEVICE Device,
    __in PVOID ConnectionParameters
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

        if (connection->PropertiesLength < sizeof(PNP_SERIAL_BUS_DESCRIPTOR))
        {
            status = STATUS_INVALID_PARAMETER;
        }
    }

    if (NT_SUCCESS(status))
    {
        descriptor = (PPNP_SERIAL_BUS_DESCRIPTOR)connection->ConnectionProperties;

        if (descriptor->SerialBusType != UART_SERIAL_BUS_TYPE)
        {
            status = STATUS_INVALID_PARAMETER;
        }
    }

    if (NT_SUCCESS(status))
    {
        uartDescriptor = (PPNP_UART_SERIAL_BUS_DESCRIPTOR)connection->ConnectionProperties; 

        // Apply the configuration settings from
        // the UART descriptor.
        ...
    }

    return status;
}
```

The PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER and PPNP_SERIAL_BUS_DESCRIPTOR pointer types in the preceding code example are defined in the Reshub.h header file.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_apply_default_configuration">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxgetconnectionparameters">SerCxGetConnectionParameters</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a>

