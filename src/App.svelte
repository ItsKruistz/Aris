<script lang="ts">
  import CircleUser from "lucide-svelte/icons/circle-user";
  import ChartLine from "lucide-svelte/icons/chart-line";
  import Package from "lucide-svelte/icons/package";
  import House from "lucide-svelte/icons/house";
  import ShoppingCart from "lucide-svelte/icons/shopping-cart";
  import Bell from "lucide-svelte/icons/bell";
  import Menu from "lucide-svelte/icons/menu";
  import Package2 from "lucide-svelte/icons/package-2";
  import Search from "lucide-svelte/icons/search";
  import Users from "lucide-svelte/icons/users";

  import { Badge } from "$lib/components/ui/badge/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import * as Card from "$lib/components/ui/card/index.js";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import * as Sheet from "$lib/components/ui/sheet/index.js";
</script>

<div class="grid min-h-screen w-full md:grid-cols-[220px_1fr] lg:grid-cols-[280px_1fr]">
  <div class="bg-muted/40 hidden border-r md:block">
    <div class="flex h-full flex-col gap-2">
      <div class="flex items-center h-12 gap-2 px-2">
        <a href="/" class="flex items-center gap-2 font-semibold">
          <Package2 class="ml-1.5" />
          <span class="sr-only">Acme Inc</span>
        </a>
        <Button size="icon" variant="ghost" class="ml-auto">
          <Bell />
          <span class="sr-only">Toggle notifications</span>
        </Button>
      </div>
      <div class="flex-1">
        <nav class="grid items-start px-1.5 gap-1.5 text-md font-medium">
          <a
            href="##"
            class="text-muted-foreground hover:text-primary flex items-center gap-3.5 rounded-lg px-2.5 py-2 transition-all"
          >
            <House class="h-5 w-5" />
            Dashboard
          </a>
          <a
            href="##"
            class="text-muted-foreground hover:text-primary flex items-center gap-3.5 rounded-lg px-2 py-2 transition-all"
          >
            <ShoppingCart class="h-5 w-5" />
            Orders
            <Badge
              class="ml-auto flex h-5 w-5 shrink-0 items-center justify-center rounded-full"
            >
              6
            </Badge>
          </a>
          <a
            href="##"
            class="bg-muted text-primary hover:text-primary flex items-center gap-3.5 rounded-lg px-2.5 py-2 transition-all"
          >
            <Package class="h-5 w-5" />
            Products
          </a>
          <a
            href="##"
            class="text-muted-foreground hover:text-primary flex items-center gap-3.5 rounded-lg px-2.5 py-2 transition-all"
          >
            <Users class="h-5 w-5" />
            Customers
          </a>
          <a
            href="##"
            class="text-muted-foreground hover:text-primary flex items-center gap-3.5 rounded-lg px-2.5 py-2 transition-all"
          >
            <ChartLine class="h-5 w-5" />
            Analytics
          </a>
        </nav>
      </div>
    </div>
  </div>
  <div class="flex flex-col">
    <header class="bg-background flex h-14 items-center gap-2 shadow shadow-neutral-200 px-2 md:h-12 md:gap-1.5 md:px-2">
      <Sheet.Root>
        <Sheet.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="shrink-0 md:hidden"
            builders={[builder]}
          >
            <Menu />
            <span class="sr-only">Toggle navigation menu</span>
          </Button>
        </Sheet.Trigger>
        <Sheet.Content side="left" class="flex flex-col border-none">
          <nav class="grid gap-1 text-md font-medium">
            <a href="##" class="flex items-center gap-3 font-semibold mb-2">
              <Package2 class="h-6 w-6 mt-[-6px] ml-[-6px]" />
              <span class="sr-only">Acme Inc</span>
            </a>
            <a
              href="##"
              class="text-muted-foreground hover:text-foreground mx-[-1rem] flex items-center gap-4 rounded-lg px-3 py-2"
            >
              <House class="h-5 w-5" />
              Dashboard
            </a>
            <a
              href="##"
              class="bg-muted text-foreground hover:text-foreground mx-[-1rem] flex items-center gap-4 rounded-lg px-3 py-2"
            >
              <ShoppingCart class="h-5 w-5" />
              Orders
              <Badge
                class="ml-auto flex h-5 w-5 shrink-0 items-center justify-center rounded-full"
              >6</Badge>
            </a>
            <a
              href="##"
              class="text-muted-foreground hover:text-foreground mx-[-1rem] flex items-center gap-4 rounded-xl px-3 py-2"
            >
              <Package class="h-5 w-5" />
              Products
            </a>
            <a
              href="##"
              class="text-muted-foreground hover:text-foreground mx-[-1rem] flex items-center gap-4 rounded-xl px-3 py-2"
            >
              <Users class="h-5 w-5" />
              Customers
            </a>
            <a
              href="##"
              class="text-muted-foreground hover:text-foreground mx-[-1rem] flex items-center gap-4 rounded-xl px-3 py-2"
            >
              <ChartLine class="h-5 w-5" />
              Analytics
            </a>
          </nav>
          <div class="mt-auto">
            <!-- Sheet footer, will add something later -->
          </div>
        </Sheet.Content>
      </Sheet.Root>
      <div class="w-full flex-1">
        <form>
          <div class="relative">
            <Search class="text-muted-foreground absolute left-2 top-2 h-5 w-5" />
            <Input
              type="search"
              placeholder="Search products..."
              class="bg-secondary w-full appearance-none pl-9 shadow-none md:w-2/3 lg:w-1/3"
            />
          </div>
        </form>
      </div>
      <DropdownMenu.Root>
        <DropdownMenu.Trigger asChild let:builder>
          <Button
            builders={[builder]}
            variant="secondary"
            size="icon"
            class="rounded-full"
          >
            <CircleUser />
            <span class="sr-only">Toggle user menu</span>
          </Button>
        </DropdownMenu.Trigger>
        <DropdownMenu.Content align="end">
          <DropdownMenu.Label>My Account</DropdownMenu.Label>
          <DropdownMenu.Separator />
          <DropdownMenu.Item>Settings</DropdownMenu.Item>
          <DropdownMenu.Item>Support</DropdownMenu.Item>
          <DropdownMenu.Separator />
          <DropdownMenu.Item>Logout</DropdownMenu.Item>
        </DropdownMenu.Content>
      </DropdownMenu.Root>
    </header>
    <main class="flex flex-1 flex-col gap-4 p-4 lg:gap-6 lg:p-6">
      <div class="flex items-center">
        <h1 class="text-lg font-semibold md:text-2xl">Inventory</h1>
      </div>
      <div class="flex flex-1 items-center justify-center rounded-xl border border-dashed">
        <div class="flex flex-col items-center gap-1 text-center">
          <h3 class="text-2xl font-bold tracking-tight">You have no products</h3>
          <p class="text-muted-foreground text-sm">
            You can start selling as soon as you add a product.
          </p>
          <Button class="mt-4">Add Product</Button>
        </div>
      </div>
    </main>
  </div>
</div>
