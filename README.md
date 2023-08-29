# git-script


@echo off

REM Get the list of differing file names

for /f %%i in ('git diff --name-only prod..test') do (

    git diff prod..test -- "%%i" > "%%~ni.diff"
    
)

echo Script completed.
