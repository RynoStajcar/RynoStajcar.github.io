---
layout: post
title:      "Using CRUD with your API"
date:       2018-04-25 15:54:22 +0000
permalink:  using_crud_with_your_api
---

In your application controller, you will be writing paths to particular pages which sends or recieves information depending on the request you have written.

Example of a path is:

***get '/' do<br></br>
erb :index<br></br>
end*** 

usually this directs you to the index.html file as a homepage. However as you build your site there are going to be different pages that take on certain responsibilities. Depending on the CRUD method you want to use there are certain requests used in order to perform the desired actions.

Create -> POST request<br></br>
Read -> GET request<br></br>
Update ->  PATCH request<br></br>
Delete -> DELETE request<br></br>

What is an API? Its the part of the server that both, recieves and sends particular requests. For example, lets say you are looking up tickets on a ticket website. You find an event you want to go to and load up the page listing all the tickets that are for sale. By loading that page you using an API to reach out to the database and retrieve certain information you are asking for.   This is done by the use of GET in a application controller, which depending on the page you are on has access to specific information. 

***get '/tickets' do<br></br>
@tickets = Ticket.all<br></br>
erb :ticket_listing<br></br>
end*** 

In the ticket_listing page you would then be able to use the variable @tickets see all the tickets and depending on what attributes you have provided in the Tickets class you could see pricing, seat location, event_id and much more. This is very simple but can be expanded on when creating forms to submit via POST request which can find matching information a tickets table. 

***post '/tickets' do<br></br>
@tickets = Ticket.find_by(params[:event_id])<br></br>
erb :ticket_listing<br></br>
end*** 

The params[:id] is information that was submitted on a page using a form. This form is located on a different page where the user has ben prompt to select from available events. Upon selecting an event, this selection would have an event_id number that would be passed through the POST request and accessible via params. Params can contain a multitude of information so as to be specific you can specify what information you want by calling on the key from the hash you want. The variable @tickets would contain only the event with the same event_id and hone your results.


Update provides a way for you to change current information without having to delete and recreate it. There is another request called PUT which you can use but PATCH is much easier to to modify specific parts since you only have to send that information through. Using PUT you need to send the whole batch of params in order to change the information. Your form uses the POST method but in the input tag ***<input id="hidden" type="hidden" name="method" value="patch">*** you want your value="patch". This will allow you to use the following request on your application controller page.

***patch '/profile/:id' do<br></br>
   @profile = Profile.find(params[:id])<br></br>
    @profile.name = params[:name]<br></br>
    @profile.birthday = params[:birthday]<br></br>
    @profile.save<br></br>
    erb :profile/:id<br></br>
  end***

This lets you change any information you want and save the new values.

The last one is pretty straight forward, delete will simply take the object you select and perform an action to delete it from the database. 

***delete '/profile/:id/delete' do<br></br>
   @profile = Profile.find(params[:id])<br></br>
    @profile.delete<br></br>
    erb :deleted<br></br>
  end***
