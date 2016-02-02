How to deploy other documents
=============================

examples for device instructions
--------------------------------

* in your project, include [fablab-document](https://github.com/fau-fablab/fablab-document) as git submodule.

```bash
git submodule add git@github.com:fau-fablab/fablab-document.git fablab-document -b master
```

* copy [`Makefile.example`](Makefile.example) to the main directory and adjust `TARGET`

```bash
DEVICE="Dev"
device="dev"
cp fablab-document/Makefile.example Makefile && sed -i 's/my_tex_main_filename__TODO__changeme/Einweisung_'${DEVICE}'/g' Makefile
```

* copy [`README.md.example`](README.md.example) to the main directory and adjust it

```bash
cp fablab-document/README.md.example README.md
sed -i 's/\$Geraet/'${DEVICE}'/g' README.md
sed -i 's/\$geraet/'${device}'/g' README.md
```

* copy [`gitignore.example`](gitignore.example) to the main direcory (`.gitignore`)

```bash
cp fablab-document/gitignore.example .gitignore
```

* check that make produces the required files in `output/`

```bash
make
```

* add the repository to the buildserver, see `macgyver.fablab.fau.de:/home/buildserver/README`
