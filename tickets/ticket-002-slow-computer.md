# Ticket 002 - Slow Computer

## User Report

The user reported that the computer was running slowly and that applications were taking a long time to open.

## Environment

- Host: Dell OptiPlex 7060
- Hypervisor: Oracle VirtualBox
- Guest OS: Windows 11 Pro
- VM Memory: 6 GB
- VM CPUs: 4
- Virtual Disk: 80 GB
- Network Mode: NAT

## Baseline

Before reproducing the issue:

- CPU: 2%
- Memory: 54%
- Disk: 0%

## Investigation

### Reproducing the Issue

Multiple Microsoft Edge tabs were opened to reproduce the reported slowdown.

Resource usage increased to:

- CPU: 46% initially, then decreased to approximately 10%
- Memory: 75%
- Disk: 4%

### Process Investigation

Task Manager was used to sort processes by memory usage.

The highest memory users included:

- Microsoft Edge
- Antimalware Service Executable
- Search

Microsoft Edge was expanded to investigate its individual processes.

The largest Edge process observed was:

- New tab: 282 MB

## Diagnosis

The temporary performance increase was associated with Microsoft Edge activity. Opening multiple Edge tabs increased memory usage from 54% to 75%.

CPU usage also temporarily increased but decreased while the system was idle.

## Resolution

The extra Microsoft Edge tabs were closed.

## Verification

After closing the extra tabs:

- CPU: 4%
- Memory: 56%
- Disk: 1%

System resource usage returned close to the original baseline.

## Skills Demonstrated

- Task Manager
- CPU monitoring
- Memory monitoring
- Disk monitoring
- Process investigation
- Identifying resource usage
- Reproducing a reported performance issue
- Comparing baseline and post-fix performance
- Documenting troubleshooting steps
