# tinyRMM - Remote Monitoring and Management, Minimally
tinyRMM is a tiny, minimal, open source Remote Monitoring and Management system that aims to live off the land and use as much native instrumentation as feasible.

## Client
The TinyRMM 'client' is a pipe connecting the output of a call to the server to powershell (windows) or shell (linux/mac) over stdout. So essentailly clientless.

## Server
The server may be broken into multiple components.
one server components is a spring app who listens for a json payload from the clientless client.
the spring app populates the database tables with information from the json payload and responds with next steps.

## Server Logic
Diagram with decision trees:
0. Start
1. New (unathenticated)
   Setup Script
2. Existing (authenticated)
   List of links to scripts (on server or git).

## Notes:
# Powershell to Invoke-Expression (iex) piped from the internet via Invoke-WebRequest (iwr)
iwr https://raw.githubusercontent.com/ardavanhashemzadeh/tinyRMM/refs/heads/main/collect-info.ps1 | iex

