# Additions to the LHCb preservation strategy

## Versions and size of LHCb software

This is a command used to compute the size of the LHCb projects:

```
$ du --si -s /cvmfs/lhcb.cern.ch/lib/lhcb/*
9.5G    /cvmfs/lhcb.cern.ch/lib/lhcb/ALIGNMENT
1.1G    /cvmfs/lhcb.cern.ch/lib/lhcb/ALIGNMENTONLINE
103G    /cvmfs/lhcb.cern.ch/lib/lhcb/ANALYSIS
9.4M    /cvmfs/lhcb.cern.ch/lib/lhcb/BEAUTYDIRAC
452M    /cvmfs/lhcb.cern.ch/lib/lhcb/BENDER
...
```

This command was used to find the number of versions:

```
for d in $(awk '{ print $2 }' project_list.dat); 
	do p=$(basename $d); 
	c=$(ls -1d $d/${p}*| wc -l); 
	echo "$p: $c versions";   
done
ALIGNMENT: 24 versions
ALIGNMENTONLINE: 14 versions
ANALYSIS: 78 versions
BEAUTYDIRAC: 5 versions
BENDER: 28 versions
...
```
