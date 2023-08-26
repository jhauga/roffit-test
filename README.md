# Roffit Test - Selective Files Test Result

Ctrl + click [test results](https://jhauga.github.io/htmlpreview.github.com/?https://github.com/jhauga/roffit-test/blob/main/index.html).

The files used for the test were either selected becuase they had elements the pull request addresses, or selected at random.
Expand below to show test files:
<details>
 <summary>Show Files Tested</summary>
  
   - brew.1
   - expr.1
   - files.txt
   - ipsec_atoasr.3
   - libssh2_sftp_readdir_ex.3
   - libssh2_userauth_publickey_sk.3
   - logtalk_allure_report.1
   - logtalk_tester.1.txt
   - mc.1.in
   - mmcli.8
   - nmap.1
   - pcap-filter.manmisc.in
   - pcap-linktype.manmisc.in
   - pidstat.1
   - quintuslgt.1
   - svnfiltereddump.1
   - xmllint.1     
</details>

I included comments in data-test (*file to build test*) where each of the below steps. They should be hard to miss.

## Test Procedure - Condensed:
1. Set configuration and ready test elements.
2. Clone source (*bagder*) and pull (*jhauga*) roffit repo.
3. Start test function configurring function for source or pull.
4. Set a start and end time for each build with roffit, pushing start and end to two separate arrays.
5. In ` run_command() ` sub-function call roffit first utilizing prior configurations to build using source or pull roffit and calculate build time(s).
   - Additional marker here cause this is where roffit is called and timed.
7. Determnin difference after all files built second in `runc_command() sub-function.
8. Call ` run_command() ` sub-function.
9. Determine if there is a difference, checking empty files and count number of differences.
10. Call ` run_test() ` function with source or pull, reconfigure and call ` run_test() ` again.
11. Make support html elements for difference output and dropdown menus.
12. Compare total fies built to files with differences, outputting results to supporting text file.
13. Calculate stats for build times, outputting results to supporting text file.
14. Make remaining support html elements and clean files and directories.
