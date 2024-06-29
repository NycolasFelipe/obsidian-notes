## Problema:
![[Pasted image 20240514172806.png]]

## Correção:
```CSS
.parent {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
}

.parent::after {
  content: "";
  flex: auto;
}
```
