def addrec(request):
    x = request.POST['first']
    y = request.POST['last']  # Corrected assignment for 'last'
    z = request.POST['country']  # Corrected assignment for 'country'
    mem = Member(firstname=x, lastname=y, country=z)
    mem.save()
    return redirect("/")

def uprec(request, id):
    mem = Member.objects.get(id=id)
    mem.firstname = request.POST['first']
    mem.lastname = request.POST['last']
    mem.country = request.POST['country']
    mem.save()
    return redirect("/")
