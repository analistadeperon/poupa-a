# poupa-a
<form #userForm="ngForm">
  <!-- Aqui está nosso form, onde declaramos a variavel userForm como ngForm--> 
  <div class="form-group">
    <label
      for="nome">Nome</label> 
      <!-- Abaixo declaramos nosso input na qual é required e onde criamos a variavel "nome" como
    ngModel (vindo de nossa entidade 'form') --> 
    <input
    type="text" class="form-control" id="nome" required #nome="ngModel" [(ngModel)]="form.nome" name="nome"> 
    <!-- Caso o campo #nome seja válido ou primitivo (caso tenha o valor inicial) este alert é ocultado--> 
    <div [hidden]="nome.valid || nome.pristine" class="alert alert-danger"> O Nome é Obrigatório </div>
  </div>
  <div class="form-group">
    <label for="idade">Idade</label> 
    <!-- Similar ao Nome apenas coloquei o minlength para validarmos também --> 
    <input type="text" class="form-control" id="idade" minlength="2" required #idade="ngModel"
    [(ngModel)]="form.idade" name="idade"> 
    <!-- Outro exemplo de verificação de validação, caso a idade seja inválida ou
    já acionada via teclado --> 
    <div class="alert alert-danger" *ngIf="idade.invalid && (idade.dirty || idade.touched)">
      <div *ngIf="idade.errors.required"> A
        Idade é obrigatória. 
      </div>
      <div
        *ngIf="idade.errors.minlength"> O tamanho máximo da idade é de
        2 numeros 
      </div>
    </div>
  </div>
  <div class="form-group">
    <label for="email">Email</label> <input type="text"
    class="form-control" id="email" [(ngModel)]="form.email"
    name="email"> 
  </div>
  <button type="submit" class="btn btn-
    success">Enviar</button> 
</form>
