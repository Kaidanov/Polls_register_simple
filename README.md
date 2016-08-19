# Polls_register_simple
Django polls project with login and registration added


Built upon 
https://docs.djangoproject.com/en/1.10/intro/tutorial01/

and 

http://www.djangobook.com/en/2.0/chapter14.html

Adding 

'''python
from django import forms
from django.contrib.auth.forms import UserCreationForm
from django.http import HttpResponseRedirect
from django.shortcuts import render

def register(request):
    if request.method == 'POST':
        form = UserCreationForm(request.POST)
        if form.is_valid():
            new_user = form.save()
            return HttpResponseRedirect("/books/")
    else:
        form = UserCreationForm()
    return render(request, "registration/register.html", {
        'form': form,
    })
'''
