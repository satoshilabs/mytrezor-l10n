How to solve weblate conflicts? 
--

(for internal use only)

It usually happens when we run extract\_strings.sh on some outdated translations, that someone changed in weblate.

How to fix it:

* in mytrezor/l10n:
    * git remote add weblate git://git.weblate.org/mytrezor.git
    * git fetch weblate
    * git checkout master
    * git reset --hard weblate/master
    * cd ../l10n\_app
    * ./extract\_strings.sh (again)
    * now proceed as normally, that is:
    * cd ../l10n
    * commit the changes, force push them to satoshilabs repo
    * change the submodule commit in mytrezor repo, commit, etc
