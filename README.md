

# Steps
##Create rails project:

    rails new ModalAjax
    gem 'twitter-bootstrap-rails'
    bundle install
    rails generate bootstrap:install static
    rails g scaffold Product name:string price:float
    rake db:migrate
    rails g bootstrap:layout
    rails g bootstrap:themed Products
    
##Create a partial contain the modal:
    <!-- Modal -->
    <div class="modal fade" id="myModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
            <h4 class="modal-title" id="myModalLabel">Modal title</h4>
          </div>
          <div class="modal-body">
            <%= render 'form' %>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>
    
##Add remote true to link_to tag:
    <%= link_to 'Edit', edit_product_path(product), :remote => true %>
    
##Add div in the layouts/aplication.html.erb to render the modal
     <div id="modal"></div>
     
##Add js.erb file to render the modal and show:   
    $('#modal').html("<%= j( render 'edit_modal' ) %>");
    $('#myModal').modal('show');

    



  
  
