<img src="https://metabake.github.io/MetaBake-Docs/logo.jpg" width="100">

## ViewModel

You can use any framework or library with Metabake. And MetaBake comes with a recommended 'app framework' for WebApps in 3 lines:


      interface iVM {
         getViewChart(name?:string):any 
         getViewList(name?:string):any 
         getViewForm(name?:string):any 
      }



This is somewhat similar to KnockOut.js M-VM-V. Major difference is that the VM for MetaBake is
what KnockOut called Complex VM or a Master VM.
Minor difference is that the M is KnockOut.js is called Services in MetaBake.

Since it is an interface and .js has no interfaces it is just to guide you: When you write a Model, it must map to the View(the entire Pug page|screen, that has *state* via query string, eg: &cust=102).
So how to use:
- Your model must map to the view!
- If you have 2 tables in your view, you should have 2 lists in the model. If you have 2 forms in view, you should have 2 object in your model. etc.
- When you read() or fetch() from binding or page, the read() | fetch() should return one of the 3 methods above.
- In you read|fetch you can use promises, callbacks or events or even flux like events.

The goal is to be as flexible as possible. When you have a form, table or chart, you must have a VM. 

(if you create includes, tags/components, you should pass the VM to it)

VM also has a dataSourceType: string = 'real'  //real or fake
The purpose is to allow development of View to be faster; and to allow for a demo if back end is b0rked.

# Other

- You should know some Firestore  already.
- Tutorial would show tabulator.js, forms

- Using ViewModel pattern to separate the data from views

- all models in assets/models that gets bind in screen/...

Demo: http://youtube.com/watch?v=B-mSA71S7VY