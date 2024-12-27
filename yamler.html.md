# <font size='+2' color='#005F6A'>**Yamler**</font>


<!-- WARNING: THIS FILE WAS AUTOGENERATED! DO NOT EDIT! -->

<a href="https://colab.research.google.com/github/frankausberlin/lazystudent/blob/main/nbs/00_Yamler.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

------------------------------------------------------------------------

<a
href="https://github.com/frankausberlin/lazystudent/blob/main/lazystudent/core.py#L9"
target="_blank" style="float:right; font-size:smaller">source</a>

### Yamler

>  Yamler (root='yamler', id_len=11, onInit={'config': False, 'files':
>              False, 'data': False}, mediator=None)

*set workingfolder, scan for yamls, load main yamls and build data
object*

``` python
#big test
!rm -rf yemler/; mkdir yemler; mkdir yemler/mathpl
!echo "test: 'hallo'" > yemler/01234567890.yml
!echo "test2: 'hallo2'" > yemler/01234567890_loop.yml
!echo "test3: 'hallo3'" > yemler/__info.yml
!echo "test4: 'hallo4'" > yemler/01234567890_de.yml
!echo "test: 'hallo'" > yemler/11234567890.yml
!echo "test2: 'hallo2'" > yemler/11234567890_loop.yml

!echo "test: 'hallo'" > yemler/mathpl/x1234567890.yml
!echo "test2: 'hallo2'" > yemler/mathpl/x1234567890_loop.yml
!echo "test3: 'hallo3'" > yemler/mathpl/__readme.yml
!echo "test4: 'hallo4'" > yemler/mathpl/x1234567890_de.yml
!echo "test: 'hallo'" > yemler/mathpl/x2234567890.yml
!echo "test2: 'hallo2'" > yemler/mathpl/x2234567890_loop.yml

y = Yamler (root='yemler')
y.activate()
# conf
y.data['01234567890']['_']['test'] += ' welta'
y.data['01234567890']['loop']['test2'] += ' weltb'
y.data['01234567890']['de']['test4'] += ' weltc'
y.config['info']['test3'] += ' weltd'
y.data['11234567890']['_']['test'] += ' weltx'
y.data['11234567890']['loop']['test2'] += ' weltb'
y.dump ()

y.activate ('mathpl')
y.data['x1234567890']['loop']['test2'] += ' weltx'
y.data['x1234567890']['de']['test4'] += ' weltx'
y.data['x1234567890']['_']['test'] += ' weltx'
y.data['x2234567890']['_']['test'] += ' weltx'
y.config['readme']['test3'] += ' weltx'
y.dump ()


print ('root:')
!cat yemler/01234567890.yml yemler/01234567890_loop.yml yemler/__conf.yml yemler/01234567890_de.yml yemler/11234567890.yml yemler/11234567890_loop.yml
print ('topic matpl:')
!cat yemler/mathpl/x1234567890.yml yemler/mathpl/x1234567890_loop.yml yemler/mathpl/__cunf.yml yemler/mathpl/x1234567890_de.yml yemler/mathpl/x2234567890.yml yemler/mathpl/x2234567890_loop.yml
```

    root:
    test: hallo welta
    test2: hallo2 weltb
    cat: yemler/__conf.yml: No such file or directory
    test4: hallo4 weltc
    test: hallo weltx
    test2: hallo2 weltb
    topic matpl:
    test: hallo weltx
    test2: hallo2 weltx
    cat: yemler/mathpl/__cunf.yml: No such file or directory
    test4: hallo4 weltx
    test: hallo weltx
    test2: 'hallo2'